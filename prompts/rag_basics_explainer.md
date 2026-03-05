# Prompt — RAG Basics for a Go Backend Engineer

ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Explain how to implement a minimal RAG pipeline and what can go wrong in production.

CONTEXT:
Audience builds APIs and cares about latency, reliability, and correctness.

INPUTS:
None.

CONSTRAINTS:

- No hype; be factual
- Include: chunking, embeddings, retrieval, prompt assembly, citations
- Mention failure modes: bad chunks, poor retrieval, context overflow, stale data

OUTPUT FORMAT:

- Markdown:
  - Minimal RAG architecture (bullets)
  - Step-by-step pipeline
  - Common failure modes + mitigations (table optional)

SUCCESS CRITERIA:

- Practical enough to start implementing a prototype
