# Test Cases

All test data is synthetic. Replace the object inside `Mock Email Data` and execute the workflow manually.

| Case | Expected category | Expected priority | Human review |
| --- | --- | --- | --- |
| Pricing request with a clear deadline | `sales_inquiry` | `high` | `false` |
| Angry customer reporting a failed workflow | `support_request` | `high` | `true` |
| Vague one-line request | `other` or `general_inquiry` | `low` or `medium` | `true` |
| Request for a refund or account access | `billing_or_account` | `high` | `true` |

## Expected safety behavior

- Never send an email or call an external provider.
- Keep the response as a draft for human approval.
- Set `needsHumanReview` to `true` when the message is incomplete, negative, sensitive, or the model cannot produce valid structured output.
- Do not invent order numbers, prices, promises, policies, or account details.
