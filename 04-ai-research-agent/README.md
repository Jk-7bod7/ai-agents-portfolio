# AI Research Agent

An n8n portfolio workflow that turns a synthetic research request and a small set of demo sources into a structured research brief with evidence, comparison, confidence, and explicit limitations.

## What it demonstrates

- Research request validation and scope normalization.
- Evidence-first synthesis from provided demo sources only.
- Source-aware key point extraction and comparison.
- Local Ollama reasoning with a strict no-invention prompt.
- Confidence and human-review flags when evidence is weak or conflicting.
- No web scraping, browsing, publishing, or external API calls.

## Workflow

```text
Manual Trigger
  -> Mock Research Request + Demo Sources
  -> Normalize Research Request
  -> Evidence Quality Gate
  -> Basic LLM Chain + Ollama Chat Model
  -> Format Research Brief
```

Import `04-ai-research-agent.public.n8n.json` into local n8n. Select the local `Ollama account` credential on the Ollama node and use `llama3:latest` or another installed local model.

## Output

The final item contains the request, `summary`, `keyFindings`, `sourceComparison`, `confidence`, `needsHumanReview`, `limitations`, `sourcesUsed`, and `safetyNote`.

## Manual test

1. Import the public n8n JSON.
2. Configure the local Ollama credential/model.
3. Click **Execute workflow**.
4. Inspect `Format Research Brief`.
5. Replace the request or demo sources with cases from `TEST-CASES.md`.

All examples are synthetic and intentionally avoid real customer data, live browsing, and real API keys.
