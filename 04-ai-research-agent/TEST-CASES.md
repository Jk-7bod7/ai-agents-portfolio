# Test Cases

All requests and sources are synthetic. Change `Mock Research Data` and execute the workflow manually.

| Case | Expected behavior |
| --- | --- |
| Two sources agree on a workflow benefit | High or medium confidence with both source IDs cited |
| Sources disagree on a metric | Conflicting evidence is called out and human review is true |
| One source has no relevant evidence | Finding is marked unsupported and confidence is reduced |
| Empty research question | Validation fails and human review is true |

## Safety expectations

- Never browse the web or call a search provider.
- Never invent facts, numbers, dates, quotes, or citations.
- Distinguish source-backed findings from assumptions.
- Keep limitations visible in the final brief.
- Do not publish or send the research automatically.
