# Customer Support Agent

An n8n portfolio workflow that analyzes a synthetic support message, classifies the issue, retrieves the relevant demo knowledge, drafts a safe response, and decides whether a human should review it.

## What it demonstrates

- Message validation and normalization.
- Deterministic escalation rules for billing, account access, angry messages, and missing context.
- Local Ollama reasoning with a small embedded demo knowledge base.
- Draft-only support replies with no external ticketing or messaging action.
- Explicit fallback behavior when the model output is invalid or the knowledge base has no answer.

## Workflow

```text
Manual Trigger
  -> Mock Support Data + Demo Knowledge Base
  -> Normalize Support Message
  -> Support Policy Gate
  -> Basic LLM Chain + Ollama Chat Model
  -> Format Support Decision
```

Import `03-customer-support-agent.public.n8n.json` into local n8n. Select the local `Ollama account` credential on the Ollama node and use `llama3:latest` or another installed local model.

## Output

The final item contains the ticket, `category`, `priority`, `sentiment`, `suggestedReply`, `needsHumanReview`, `escalationReason`, `knowledgeUsed`, and `safetyNote`.

## Manual test

1. Import the public n8n JSON.
2. Configure the local Ollama credential/model.
3. Click **Execute workflow**.
4. Inspect `Format Support Decision`.
5. Replace the mock message with cases from `TEST-CASES.md`.

All examples use synthetic data and `.test` addresses.
