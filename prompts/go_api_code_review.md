# Prompt — Go API: Code Review Checklist (Mid-level)

ROLE:
You are a senior software assistant performing a pragmatic code review for a Mid-level Go backend engineer.

OBJECTIVE:
Review the provided Go code and propose improvements with a focus on correctness, simplicity, and production readiness.

CONTEXT:

- Code belongs to a small Go API using net/http and internal packages.
- Prefer minimal changes with high impact.

INPUTS:

- Paste code (or file diffs) here:
  {CODE_OR_DIFFS}

CONSTRAINTS:

- Be specific: point to exact lines or patterns
- Prioritize issues: P0 (must-fix), P1, P2
- Avoid style bikeshedding
- Suggest concrete fixes (snippets)
- Consider: error handling, timeouts, input validation, JSON encoding, logging, testability

OUTPUT FORMAT:

- Markdown:
  - Summary (3 bullets max)
  - Findings (grouped by P0/P1/P2)
  - Suggested patch snippets (small and targeted)

SUCCESS CRITERIA:

- Actionable, minimal, realistic improvements
- No invented packages/APIs
