# Prompt — Go API: Add POST /ai/summarize (Local LLM)

ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Add a new endpoint POST /ai/summarize to an existing Go API (Gin + zerolog) that calls a local LLM (Ollama) via HTTP and returns a short summary.

CONTEXT:

- Current API uses Gin and zerolog.
- Existing endpoint: GET /health returns {"status":"ok"}.
- Config is loaded via config.Load() and includes port and timeouts.
- We want to add configuration via env:
  - LLM_BASE_URL (e.g. http://localhost:11434 for Ollama)
  - LLM_MODEL (exact model name)
  - AI_TIMEOUT (e.g. 20s)
- Keep the design minimal and idiomatic.
- The endpoint must be resilient: input validation, timeouts, clean error responses.

INPUTS:

- Current router wiring (main.go) and current structure:
  - cmd/api/main.go wires routes
  - internal/handlers contains handlers
- Choose one provider implementation to support first Ollama API

CONSTRAINTS:

- Keep Gin + zerolog.
- Use standard library net/http for the outbound call.
- Add request/response structs (no map[string]any).
- Limit summary to ~5 bullet points OR <= 120 words (choose one and enforce via prompt).
- Do not log full user input text (privacy). Log only length and request id if you add one.
- Return proper HTTP status codes:
  - 400 for bad input
  - 502 if LLM call fails
  - 200 on success

OUTPUT FORMAT:
Provide full contents (or minimal diffs) for these files:

1. cmd/api/main.go (route wiring)
2. internal/handlers/ai.go
3. internal/services/ai_summarize.go (or internal/llm/client.go if you prefer)
4. internal/config/config.go (extend config to include LLM_BASE_URL, LLM_MODEL, AI_TIMEOUT)
5. configs/.env.example (add the new env vars)

Also provide:

- curl example for calling the endpoint
- short note (max 5 bullets) describing changes

SUCCESS CRITERIA:

- `go run ./cmd/api` works
- `curl -X POST /ai/summarize ...` returns {"summary":"..."}
- Code is minimal, readable, and production-minded
