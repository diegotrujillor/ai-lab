# Prompt — Go API: Create a New Endpoint (Mid-level)

ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Generate a new HTTP endpoint for an existing Go API, following the repo structure and keeping code idiomatic.

CONTEXT:

- Repo structure:
  - cmd/api/main.go (server bootstrap)
  - internal/handlers (HTTP handlers)
  - internal/services (use cases)
  - internal/domain (entities/business rules)
- Current API includes GET /health returning {"status":"ok"}.
- Use standard library only unless explicitly allowed.

INPUTS:

- Endpoint description: {describe_endpoint_here}
- HTTP method + path: {METHOD} {PATH}
- Request body (if any): {JSON schema or example}
- Response body: {JSON schema or example}

CONSTRAINTS:

- Language: Go
- Standard library only
- Provide complete file contents or minimal diffs per file (state which)
- Validate inputs and return proper status codes
- Set Content-Type to application/json
- Keep handlers thin; move logic into services when relevant
- Add basic error handling

OUTPUT FORMAT:

- Markdown with sections:
  1. Files to add/change
  2. Code blocks per file path (full content)
  3. How to run & test quickly (curl examples)

SUCCESS CRITERIA:

- Code compiles
- Endpoint returns correct status codes and JSON
- Clear separation handler/service
