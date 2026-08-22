# TraceRoot Signal Pipeline

Built for the TraceRoot GTM Engineer Intern application, the "link to something you built."

## Screenshot

<img width="1401" height="387" alt="image" src="https://github.com/user-attachments/assets/fd3fd93e-f619-4673-8e1f-169628f6d7d5" />


## What it does

Finds teams building AI agents who are showing real, public debugging pain, GitHub issues, Show HN posts, Discord threads, not generic content about agents.

Three stages, in n8n:

1. **Discovery** — daily search, filtered by a classifier that rejects generic content, unconfirmed entities, and AI-generated sources.
2. **Enrichment** — a factual check on the person behind the signal and one recent company data point, no speculation.
3. **Draft outreach** — a short, specific message written from the confirmed pain, using only what was actually found.

Nothing sends automatically. Every draft lands in a spreadsheet marked "Awaiting review."

## Example output

```json
{
  "team_or_project_name": "Test Corp",
  "pain_confirmed": true,
  "pain_summary": "Agent crashes intermittently in production, hard to trace root cause",
  "potential_champion": "Jane Doe, Lead Engineer",
  "source_url": "https://github.com/example/repo/issues/1",
  "confidence": "high"
}
```

## Not the first time

Same three-stage architecture, adapted, not copy-pasted, for two other outbound projects this month, one for an ASIC inference chip company, one for an AI inference platform. Different ICP each time, same underlying discipline: verify before it reaches a human, never send without review.

## What I got wrong building it

First test used too broad a search topic and returned nothing, not a bug, just a bad test. A JSON-parsing step also broke the first time a model response included any extra text around the data, fixed with a more robust extraction instead of a fragile regex.

## Import

Import `TraceRoot_Signal_Pipeline (2).json` directly into n8n. Requires Anthropic, Linkup, Slack, and Google Sheets credentials.
