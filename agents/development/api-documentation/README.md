# Swagger - The API Documentation Generator

> Your AI agent that reads your codebase and generates production-ready OpenAPI documentation.

## Overview

Swagger scans your API codebase and produces complete documentation:

- Generates OpenAPI 3.0 specs from route definitions
- Writes cURL and SDK examples for every endpoint
- Detects documentation drift when code changes
- Flags breaking changes between versions

## Quick Start

### Installation

```bash
mkdir -p ~/.openclaw/agents/api-documentation/agent
cp SOUL.md ~/.openclaw/agents/api-documentation/agent/

openclaw agents add api-documentation --workspace ~/.openclaw/agents/api-documentation
```

### First Conversation

```bash
openclaw chat api-documentation "Document all endpoints in /src/routes/"
```

## Use Cases

### 1. Full API Documentation
```
You: Document our Express API
Swagger: [Generates openapi.yaml with all endpoints, schemas, and examples]
```

### 2. Breaking Change Detection
```
You: What changed since v2.3?
Swagger: [Lists new, changed, removed, and breaking endpoints with details]
```

### 3. Documentation Validation
```
You: Are our docs up to date?
Swagger: [Sync report showing coverage %, drift, and missing docs]
```

### 4. SDK Example Generation
```
You: Generate Python examples for the /users endpoints
Swagger: [Python requests snippets for each endpoint with error handling]
```

## Example Output

### OpenAPI Spec

```yaml
openapi: 3.0.1
info:
  title: My API
  version: 2.4.0
paths:
  /api/v1/users:
    get:
      summary: List all users
      parameters:
        - name: page
          in: query
          schema: { type: integer, default: 1 }
      responses:
        200:
          description: Paginated user list
```

### Sync Report

```
API Documentation Sync Report
STATUS: 47/49 endpoints documented (95.9%)
BREAKING CHANGES: 1
DRIFT DETECTED: 1
NEW UNDOCUMENTED: 2
```

## Tips

1. **Point to your routes directory** for the most accurate scan
2. **Run on every PR** to catch documentation drift early
3. **Include type definitions** (TypeScript, Pydantic) for better schema extraction
4. **Use tags** to organize endpoints by resource group

## Changelog

- **v1.0.0** - Initial release with OpenAPI generation
- **v1.1.0** - Breaking change detection
- **v1.2.0** - Multi-language SDK examples

## Author

Created by [@openclaw](https://github.com/openclaw)

## License

MIT
