# Prompt — Evaluation Rubric (LLM outputs)

ROLE:
You are a senior evaluator.

OBJECTIVE:
Score the model output using a simple rubric and provide improvement suggestions for the prompt.

CONTEXT:
We are evaluating outputs for:

- Go code generation
- Summaries/explanations for backend engineers

INPUTS:

- Task prompt:
  {PROMPT_USED}
- Model output:
  {MODEL_OUTPUT}

CONSTRAINTS:

- Use 1–5 scale
- Be strict but fair
- Recommend prompt improvements (not model changes)

OUTPUT FORMAT:

- Markdown:
  - Scores: Correctness, Completeness, Clarity, Practicality, Safety
  - Key issues (bullets)
  - Prompt improvement suggestions (bullets)

SUCCESS CRITERIA:

- Repeatable scoring + actionable prompt edits
