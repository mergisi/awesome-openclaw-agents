---
name: music-generate
description: Trigger when the user asks for generated music, a background track, a jingle, an intro or outro sting, an instrumental bed, a song from supplied lyrics, or a cover of an existing recording, or says "/music-generate". Calls the MiniMax music generation endpoint and writes the returned audio to a file.
---

# Music Generate

Bundled integration for the MiniMax music generation endpoint. This is the concrete request and
response contract behind the `music_generate` capability referenced by the
[Music Producer](../../../agents/creative/music-producer/SOUL.md) template, so an agent can produce a
track with one HTTP call instead of depending on a separate command line tool.

## When to use

- "Generate background music for this video"
- "Make a 5 second jingle for our podcast intro"
- "Turn these lyrics into a song"
- "I need an instrumental ambient bed"
- "Make a cover of this recording"
- `/music-generate <brief>`

## Setup

```bash
# API key for your account
export MINIMAX_API_KEY=your-api-key-here

# Pick the endpoint for your service region
export MINIMAX_MUSIC_URL=https://api.minimax.io/v1/music_generation   # global
# export MINIMAX_MUSIC_URL=https://api.minimaxi.com/v1/music_generation   # mainland China
```

## Endpoints

| Region | Endpoint | Documentation |
|---|---|---|
| Global | `https://api.minimax.io/v1/music_generation` | [API reference](https://platform.minimax.io/docs/api-reference/music-generation) |
| Mainland China | `https://api.minimaxi.com/v1/music_generation` | [API reference](https://platform.minimaxi.com/docs/api-reference/music-generation) |

Both regions expose the same `generateMusic` operation over `POST` with an
`Authorization: Bearer <key>` header and a `Content-Type: application/json` body.
Accounts are region-scoped: use the key issued for the region whose endpoint you call.

## Models

| Task | Model IDs |
|---|---|
| Text to music | `music-3.0` (default), `music-2.6`, `music-3.0-free`, `music-2.6-free` |
| Cover an existing recording | `music-cover`, `music-cover-free` |

Use `music-3.0` unless the user asks for something else. The `-free` variants run the same
interface at a much lower rate limit, so prefer them only for a smoke test.

## Request fields

| Field | Notes |
|---|---|
| `model` | **Required.** One of the model IDs above. |
| `prompt` | Style, mood, instrumentation, and scenario. Required for instrumental text-to-music and for the cover models. |
| `lyrics` | Lyric lines separated by `\n`. Required for vocal text-to-music. Section tags such as `[Intro]`, `[Verse]`, `[Chorus]`, `[Bridge]`, `[Outro]` are supported. |
| `stream` | Boolean, defaults to `false`. Streamed responses accept only `output_format: hex`. |
| `output_format` | `url` / `hex`. `hex` returns the audio inline as a hex string; `url` returns a link that expires after 24 hours. |
| `audio_setting` | Object controlling the rendered file. See the table below. |
| `lyrics_optimizer` | Boolean, defaults to `false`. Writes lyrics from `prompt` when `lyrics` is empty. Text-to-music models only. |
| `is_instrumental` | Boolean, defaults to `false`. Produces a vocal-free track, so `lyrics` is not needed. Text-to-music models only. |
| `audio_url` | Cover models only. Link to the reference recording. |
| `audio_base64` | Cover models only. The same recording inlined as base64. |
| `cover_feature_id` | Cover models only. Reuses a previously preprocessed reference instead of re-uploading audio. |

`audio_setting` sub-fields:

| Sub-field | Type | Allowed values |
|---|---|---|
| `sample_rate` | integer | `16000`, `24000`, `32000`, `44100` |
| `bitrate` | integer | `32000`, `64000`, `128000`, `256000` |
| `format` | string | `mp3` / `wav` / `pcm` |

### Cover input rules

- Supply exactly one of `audio_url` or `audio_base64`, or a `cover_feature_id` from a previous
  preprocess call. Sending more than one is rejected.
- The reference recording must run between 6 and 360 seconds and stay under 50 MB.

### Region-specific fields

- `aigc_watermark` is accepted only by the mainland China endpoint. Do not send it to the
  global endpoint, which rejects unknown fields.

## Response mapping

| What you need | Where it is |
|---|---|
| Call succeeded | `base_resp.status_code` equals `0`; anything else is an error, and `base_resp.status_msg` carries the reason |
| Generation finished | `data.status` equals `2` (`1` means still rendering) |
| Audio payload | `data.audio` |

The call is synchronous: there is no task id and no separate query endpoint, so never poll.
Check `base_resp.status_code` first, then `data.status`, then read the audio out of `data.audio`.
With `output_format: hex` the value in `data.audio` is hex text that you decode to bytes yourself;
with `output_format: url` it is a link that expires after 24 hours, so download it immediately.

## Instructions

1. Ask for mood, genre, tempo, and intended length before the first call unless the user
   already gave them. One clarifying round, then generate.
2. Build the body: `model`, a descriptive `prompt`, and either `lyrics` or
   `is_instrumental: true`. Set `lyrics_optimizer: true` only when the user wants vocals but
   has no lyrics.
3. Send the request:

```bash
curl -sS "$MINIMAX_MUSIC_URL" \
  -H "Authorization: Bearer $MINIMAX_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "music-3.0",
    "prompt": "warm electronic synth bed, 120 BPM, building energy, product launch",
    "is_instrumental": true,
    "output_format": "hex",
    "audio_setting": {"sample_rate": 44100, "bitrate": 256000, "format": "mp3"}
  }' > response.json
```

4. Verify the call, then decode the track:

```bash
python3 -c "import json;d=json.load(open('response.json'));\
assert d['base_resp']['status_code'] == 0, d['base_resp']['status_msg'];\
assert d['data']['status'] == 2, 'still rendering';\
open('track.mp3','wb').write(bytes.fromhex(d['data']['audio']))"
```

5. Report the saved path, the model used, and the audio settings. When the user asked for
   variations, change one dimension at a time (tempo, instrumentation, energy) and keep the
   rest of the body identical so the results stay comparable.

## Rules

- Never echo the API key, and never paste it into the request body.
- Keep `prompt` descriptive rather than naming a copyrighted work to imitate.
- Match `audio_setting.format` to the delivery target: `mp3` for general sharing,
  `wav` for further editing, `pcm` for raw pipelines.
- For streaming set `stream: true` and `output_format: hex`; the other output format is not
  available while streaming.

## Example invocations

- `/music-generate 45s inspiring synth bed for a product launch video`
- "Make me a 5 second podcast intro jingle, bright and acoustic"
- "Sing these lyrics as a slow ballad"
