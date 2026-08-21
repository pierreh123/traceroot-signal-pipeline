# TraceRoot Signal Pipeline

Built for the TraceRoot GTM Engineer Intern application, the "link to something you built."

## What it does

Finds teams building AI agents who are showing real, public debugging pain, GitHub issues, Show HN posts, Discord threads, not generic content about agents.

Three stages, in n8n:
1. **Discovery** — daily search, filtered by a classifier that rejects generic content, unconfirmed entities, and AI-generated sources.
2. **Enrichment** — a factual check on the person behind the signal and one recent company data point, no speculation.
3. **Draft outreach** — a short, specific message written from the confirmed pain, using only what was actually found.

Nothing sends automatically. Every draft lands in a spreadsheet marked "Awaiting review."

## What I got wrong building it

First test used too broad a search topic and returned nothing, not a bug, just a bad test. A JSON-parsing step also broke the first time a model response included any extra text around the data, fixed with a more robust extraction instead of a fragile regex.

## Import

Import `TraceRoot_Signal_Pipeline_v2.json` directly into n8n. Requires Anthropic, Linkup, Slack, and Google Sheets credentials.# traceroot-signal-pipeline
