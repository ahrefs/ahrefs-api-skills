# Ahrefs API Skills

[Claude Code](https://docs.anthropic.com/en/docs/claude-code) skills for the [Ahrefs API](https://docs.ahrefs.com/docs/api/v3/) and [Python SDK](https://github.com/ahrefs/ahrefs-python).

Skills teach your AI coding assistant the SDK's patterns, available methods, and best practices — so it can write correct Ahrefs API code without guessing.

## Prerequisites

Install the [Ahrefs Python SDK](https://github.com/ahrefs/ahrefs-python) and set your API key:

```sh
pip install git+https://github.com/ahrefs/ahrefs-python.git
export AHREFS_API_KEY="your-api-key"
```

## Installation

```sh
npx skills add ahrefs/ahrefs-api-skills --skill ahrefs-python --global
```

Then ask Claude Code to use the Ahrefs API — it will know the SDK patterns, all 52 methods, error handling, and filter syntax.

## What's included

The `ahrefs-python` skill provides:

- **SDK usage rules** — always use the typed client, correct response access patterns, date formats
- **All 52 API methods** — Site Explorer, Keywords Explorer, Rank Tracker, Site Audit, Brand Radar, SERP Overview, Batch Analysis
- **Filter syntax reference** — BNF grammar and examples for building query filters

## Links

- [Ahrefs Python SDK](https://github.com/ahrefs/ahrefs-python) — the Python library itself
- [Ahrefs API docs](https://docs.ahrefs.com/docs/api/v3/) — official API documentation
