# Prompt Examples (Week 1)

This document contains ready-to-run prompt examples based on the reusable template in `prompts/template.md`.

Use these to:

- establish a consistent baseline across models,
- compare outputs week by week,
- and keep prompts reproducible.

---

## Example A — Minimal Go `net/http` Health Endpoint

```text
ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Create a minimal HTTP server with GET /health returning JSON {"status":"ok"}.

CONTEXT:
- Repo uses cmd/api/main.go and internal/handlers.
- Must compile and run on localhost.
- Use net/http only.

INPUTS:
None.

CONSTRAINTS:
- Language: Go
- Standard library only
- Return Content-Type: application/json
- Keep it simple and readable
- Provide complete code (no pseudo-code)

OUTPUT FORMAT:
- Provide file contents for:
  1) cmd/api/main.go
  2) internal/handlers/health.go
- No extra commentary outside code blocks.

SUCCESS CRITERIA:
- `go run ./cmd/api` works
- `curl localhost:8080/health` returns {"status":"ok"}
```

## Example B — RAG vs Fine-tuning (Practical Explanation)

Use this prompt to get a **concise, practical** comparison between RAG and fine-tuning from the perspective of a **Mid-level Go backend engineer** building production APIs.

---

### Prompt (copy/paste)

```text
ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Explain the difference between RAG and fine-tuning in a practical way for a backend engineer.

CONTEXT:
Audience is a backend engineer building APIs. Keep it concise.

INPUTS:
None.

CONSTRAINTS:
- No hype; be factual
- Provide 3 scenarios where RAG is better and 3 where fine-tuning is better
- Keep it concise, but specific
- Use production-minded considerations (latency, cost, privacy, maintenance)

OUTPUT FORMAT:
- Markdown with:
  - Definitions (2–3 lines each)
  - When to use RAG (3 bullets)
  - When to fine-tune (3 bullets)
  - Quick decision checklist (max 5 bullets)

SUCCESS CRITERIA:
- Clear, practical, no jargon overload
- Scenarios are realistic for production systems
- Checklist is actionable for choosing an approach
```
