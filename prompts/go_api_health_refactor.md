# Prompt — Go API: Refactor /health to a clean handler

ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Refactor the existing /health endpoint into internal/handlers while keeping behavior identical.

CONTEXT:

- Current code has GET /health returning {"status":"ok"}.
- Repo structure should be:
  - cmd/api/main.go wires routes + server
  - internal/handlers contains health handler

INPUTS:

- Current main.go:
  {PASTE_CURRENT_MAIN_GO}

CONSTRAINTS:

- Standard library only
- Keep response exactly: {"status":"ok"}
- Ensure Content-Type: application/json
- Keep changes minimal and idiomatic

OUTPUT FORMAT:

- Provide full contents for:
  1. cmd/api/main.go
  2. internal/handlers/health.go
- Include a curl command to verify

SUCCESS CRITERIA:

- `go run ./cmd/api` works
- `curl localhost:8080/health` returns {"status":"ok"}
