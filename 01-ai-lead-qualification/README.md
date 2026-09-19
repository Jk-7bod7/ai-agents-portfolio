# AI Lead Qualification

Local n8n portfolio project for qualifying demo leads with mock data only.

## Scope

- No real customer data
- No real API keys
- Runs locally in n8n
- Produces a score, classification, and explanation for each demo lead

## Current workflow in n8n

Manual Trigger -> Edit Fields (JSON mock lead) -> Code (score and classify)
                                                   -> Basic LLM Chain -> Ollama Chat Model

## Current test result

The demo lead `Sara Hassan` from `Demo Startup` was processed successfully:

- Qualification score: `100/100`
- Classification: `Hot Lead`
- Input email: `sara@example.test` (test-only domain)

The scoring rules award points for budget, timeline, problem clarity, and
company size. Required-field validation now routes incomplete leads to
`Needs Review` instead of scoring them. A local `Ollama Chat Model` is connected to `Basic LLM Chain`
using the installed `llama3:latest` model. No cloud provider or real API key is
used.

## Verified end-to-end result

The complete n8n workflow executed successfully. The rule-based output was
`100/100` and `Hot Lead`, and Ollama generated a summary and next action from
the same mock lead. The validation and classification branches are covered in
the Code node: `Hot Lead` (75+), `Warm Lead` (50-74), `Cold Lead` (1-49), and
`Needs Review` (missing required fields or zero score).

## Import and portfolio use

Import `01-ai-lead-qualification.public.n8n.json` into a local n8n instance.
After import, select or create a local Ollama credential and choose an
installed local model. The public export intentionally contains no credential
secret. See `TEST-CASES.md` for manual demo scenarios.

## Visuals

- [Workflow overview](./screenshots/workflow-overview.svg)
- [Qualification output](./screenshots/qualification-output.svg)

## Limitations

This is a portfolio demo, not a production CRM integration. It does not send
emails, write to a CRM, or process real customer data. Production use would
need authentication, observability, rate limits, privacy controls, and a
reviewed scoring policy.
