# ai-lab

Experiments and notes for local LLMs, RAG, agents, and evaluation.

## Week 1 - Day 1 Baseline (Local LLM)

### Setup

- Tool: (LM Studio / Ollama)
- Model: (exact name + quant if applicable)
- Machine: (RAM/CPU/GPU optional)
- Notes: (anything relevant: context length, temperature, etc.)

### Baseline Prompts

#### 1) Summarization

- Prompt: Summarize the following in 5 bullet points...
- Output (short): accurate, with fews chances of improvement
- Latency (approx): <1s
- Quality (1-5): 4

#### 2) Go endpoint generation

- Prompt: Create a minimal Go net/http server with GET /health...
- Output (short): very basic but is okay
- Compiles: (yes/no) yes
- Latency (approx): <1s
- Quality (1-5): 4

#### 3) RAG vs Fine-tuning

- Prompt: Explain the difference between RAG and fine-tuning...
- Output (short): acceptable but fine, confusion between RAG and TAG, I had to give more context
- Latency (approx): <2s
- Quality (1-5): 3

### Initial Takeaways

- Strengths:
- Weaknesses:
- Next step (Week 1 Day 2):
