# AI Email Assistant

An n8n portfolio workflow that analyzes a synthetic inbound email, classifies its intent and urgency, extracts the requested action, drafts a professional reply, and flags messages that need human review.

## What it demonstrates

- Input validation and normalization before an AI call.
- Structured intent, priority, sentiment, and action extraction.
- Local Ollama inference through n8n's Basic LLM Chain.
- Safe draft-only behavior: the workflow never sends an email.
- A deterministic review gate for missing context, negative sentiment, or sensitive requests.

## Workflow

```text
Manual Trigger
  -> Mock Email Data
  -> Normalize Email
  -> Basic LLM Chain + Ollama Chat Model
  -> Format Email Decision
```

The public export is `02-ai-email-assistant.public.n8n.json`. It contains no credentials or real customer data. After importing it into local n8n, select the local `Ollama account` credential on the Ollama node and use `llama3:latest` (or another locally installed model).

## Output

The final item includes the original demo email, `category`, `priority`, `sentiment`, `customerRequest`, `suggestedReply`, `needsHumanReview`, `reviewReasons`, and `safetyNote`.

## Manual test

1. Import the public JSON into local n8n.
2. Open the `Ollama Chat Model` node and select a local Ollama credential/model.
3. Click **Execute workflow**.
4. Inspect the output of `Format Email Decision`.
5. Try the cases in `TEST-CASES.md` by changing the mock email in `Mock Email Data`.

All examples are synthetic and use `.test` email addresses.
