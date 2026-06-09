# LLM Quality Suite 🤖

AI/LLM test suite for a fintech assistant — built with PromptFoo + Ollama (llama3.2).

## What This Tests

| Dimension | Tests | Description |
|---|---|---|
| ✅ Factual Accuracy | 3 | UPI definition, limits, resolution steps |
| 🚫 Safety Guardrails | 2 | Fraud refusal, phishing refusal |
| 📏 Format Validation | 1 | Structured response format |
| 🔍 Hallucination Detection | 4 | Minimum limit, consistency, edge cases, prompt injection |

## Results
10/10 tests passing (100%) — Duration: 3s — Concurrency: 4

## Key Engineering Decision
Hallucination detection required two-layer validation:
1. LLM rubric specifying exact correct answer (Re 1 minimum UPI amount)
2. Deterministic not-icontains assertions blocking common wrong values (100, 500)

This combination ensures reliable evaluation of non-deterministic LLM output.

## Run Locally
\`\`\`bash
npm install
ollama pull llama3.2
npx promptfoo eval
\`\`\`

## Tech Stack
- PromptFoo — LLM evaluation framework
- Ollama llama3.2 — local LLM provider
- Temperature: 0.1 — low randomness for consistent fintech responses