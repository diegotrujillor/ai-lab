# Week 1 — Day 3: Local LLM Summarize Endpoint — Short Note

- Added a prompt to generate a Go API endpoint `POST /ai/summarize` backed by a local Ollama model (`llama3.1`).
- Included env-driven configuration: `LLM_BASE_URL`, `LLM_MODEL`, and `AI_TIMEOUT`.
- Enforced input validation and privacy-friendly logging (no raw text in logs).
- Standardized request/response shapes for repeatable evaluation.
- Provided curl examples to verify end-to-end behavior.
