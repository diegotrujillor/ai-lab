# Prompt Template (Reusable)

Use this template to keep prompts **repeatable, testable, and production-oriented**.  
Goal: reduce ambiguity, minimize hallucinations, and enforce consistent output.

---

## 1) Prompt Header

### Role

You are a senior software assistant helping a **Mid-level Go backend engineer**.

### Objective

What you want the model to do in one sentence.

### Context

Only the information the model needs. Include constraints and relevant details.

### Inputs

- Paste input data or reference it clearly
- If there are multiple inputs, list them

### Constraints

- Language: **Go**
- Use: **standard library only** unless explicitly allowed
- Be explicit about assumptions; if missing info, say what’s missing
- Avoid placeholders like “someFunction()” unless you provide the full implementation
- Security: never expose secrets; prefer safe defaults
- Performance: keep it simple and efficient; avoid unnecessary allocations
- Style: idiomatic Go, small functions, clear names

### Output Format

Specify exactly what you want back: code only, markdown sections, JSON, etc.

### Success Criteria

- How you will judge the output
- Example: “Compiles”, “Has tests”, “Handles errors”, “No external deps”

---

## 2) Prompt Body (Fill-in)

Copy/paste and fill the fields:

```text
ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
{one_sentence_goal}

CONTEXT:
{key_context}
{repo_structure_if_relevant}
{runtime_constraints_if_any}

INPUTS:
{inputs_or_data}

CONSTRAINTS:
- Language: Go
- Standard library only (unless I explicitly allow other libraries)
- If information is missing, list what you need and proceed with safe assumptions
- Do not invent APIs or packages that don’t exist
- Provide complete, compilable code (no pseudo-code)
- Add basic error handling and sensible defaults
- Keep output concise and structured

OUTPUT FORMAT:
{exact_format_required}

SUCCESS CRITERIA:
{bullet_list_of_acceptance_criteria}
```
