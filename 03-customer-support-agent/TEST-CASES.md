# Test Cases

All messages and policies are synthetic. Change `Mock Support Data` and execute the workflow manually.

| Case | Expected category | Expected review |
| --- | --- | --- |
| “The dashboard export is empty” | `technical` | `false` |
| “I want a refund for my subscription” | `billing` | `true` |
| “I cannot access my account” | `account` | `true` |
| “Your product is useless and I am furious” | `general` or `technical` | `true` |
| “Please help” with no details | `general` | `true` |

## Safety expectations

- Never send a support reply or update a ticket.
- Never invent policy, refund decisions, timelines, or account facts.
- Use the demo knowledge base only as guidance.
- Escalate sensitive, angry, unclear, billing, and account-access requests.
