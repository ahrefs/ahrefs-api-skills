---
name: ahrefs-python
description: Manages Ahrefs API usage in Python using `ahrefs-python` library. Use when working with SEO / marketing related tasks or with data including backlinks, keywords, domain ratings, organic traffic, site audits, rank tracking, brand monitoring, web analytics (page views, visitors, traffic sources, referrers, devices), and project management (keyword lists, competitors). Covers `ahrefs-python` usage including AhrefsClient / AsyncAhrefsClient, typed request/response models, error handling, and all API sections. Trigger this skill whenever the user mentions Ahrefs, ahrefs-python, or any SEO data retrieval task in Python.
---

# Ahrefs Python SDK Skill

## Overview

The Ahrefs API provides programmatic access to Ahrefs SEO data. The official Python SDK (`ahrefs-python`) provides typed request and response models for all endpoints, auto-generated from the OpenAPI spec.

Key capabilities:
- **Site Explorer** - Backlinks, organic keywords, domain rating, traffic, referring domains
- **Keywords Explorer** - Keyword research, volumes, difficulty, related terms
- **Management** — Rank Tracker project, keyword list, and competitor management (create, update, delete)
- **Rank Tracker** - SERP monitoring, competitor tracking
- **Site Audit** - Technical SEO issues, page content, page explorer
- **Brand Radar** - AI brand mentions, share of voice, impressions
- **SERP Overview** - Search result analysis
- **Batch Analysis** - Bulk domain/URL metrics via POST
- **Web Analytics** - Website visitor analytics (traffic, browsers, devices, sources, pages)
- **Public** — Ahrefs crawler IP addresses and CIDR ranges
- **Subscription Info** — API usage limits, billing period, key expiration

## Installation

```sh
pip3 install git+https://github.com/ahrefs/ahrefs-python.git
```

Requires Python 3.11+. Dependencies: `httpx`, `pydantic`.

## API Method Discovery

The SDK has 102 methods across 11 API sections. The built-in search tool is the fastest way to find the right method — it returns matching method signatures, parameters, and return types directly, so there's no need to scan through a large reference.

**Python** (preferred when already in a Python context):

```python
from ahrefs.search import search_api_methods

# Returns formatted text with method signatures, parameters, and return types
print(search_api_methods("domain rating"))

# Filter by API section and limit results
print(search_api_methods("backlinks", section="site-explorer", limit=3))
```

**CLI** (preferred when exploring from the terminal):

```sh
# Ensure python3 points to the interpreter where ahrefs-python is installed:
#   which python3
#   python3 -c "import ahrefs"
python3 -m ahrefs.api_search "domain rating"
python3 -m ahrefs.api_search "backlinks" --section site-explorer --limit 3
python3 -m ahrefs.api_search "batch" --json
python3 -m ahrefs.api_search --sections  # list all API sections
```

## IMPORTANT RULES

- ALWAYS use the `ahrefs-python` SDK. DO NOT make raw `httpx`/`requests` calls to the Ahrefs API.
- ALWAYS pass dates as strings in `YYYY-MM-DD` format (e.g. `"2025-01-15"`).
- ALWAYS use `select` on list endpoints to request only the columns you need. List endpoints return all columns by default, which wastes API units and increases response size.
- USE context managers (`with` / `async with`) for client lifecycle management.
- NEVER hardcode API keys in source code. Use the `AHREFS_API_KEY` environment variable or your preferred secrets mechanism.
- The client handles retries (429, 5xx, connection errors) automatically. DO NOT implement your own retry logic on top of the SDK.

## Quick Start

```python
import os
from ahrefs import AhrefsClient

with AhrefsClient(api_key=os.environ["AHREFS_API_KEY"]) as client:
    data = client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")
    print(data.domain_rating)  # 91.0
    print(data.ahrefs_rank)    # 3
```

## SDK Patterns

### Client Setup

```python
import os
import ahrefs

with ahrefs.AhrefsClient(
    api_key=os.environ["AHREFS_API_KEY"],  # or any secrets source
    base_url="...",          # override API base URL (default: https://api.ahrefs.com/v3)
    timeout=30.0,            # request timeout in seconds (default: 60)
    max_retries=3,           # retries on transient errors (default: 2)
) as client:
    ...
```

Async client:

```python
import os
from ahrefs import AsyncAhrefsClient

async with AsyncAhrefsClient(api_key=os.environ["AHREFS_API_KEY"]) as client:
    data = await client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")
```

For parallel calls, use `asyncio.gather`:

```python
import asyncio

async with AsyncAhrefsClient(api_key=os.environ["AHREFS_API_KEY"]) as client:
    dr_ahrefs, dr_moz = await asyncio.gather(
        client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15"),
        client.site_explorer_domain_rating(target="moz.com", date="2025-01-15"),
    )
```

### Calling Methods

Two calling styles -- both are equivalent:

```python
# Keyword arguments (recommended)
data = client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")

# Request objects (full type safety)
from ahrefs.types import SiteExplorerDomainRatingRequest
request = SiteExplorerDomainRatingRequest(target="ahrefs.com", date="2025-01-15")
data = client.site_explorer_domain_rating(request)
```

Method names follow `{api_section}_{endpoint}`, e.g. `site_explorer_organic_keywords`, `keywords_explorer_overview`.

### Responses

Methods return typed Data objects directly.

**Scalar endpoints** return a single data object (or `None`):

```python
data = client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")
print(data.domain_rating)
```

**List endpoints** return a list of data objects. There is no pagination — set `limit` to the number of results you need. Use `select` to request only the columns you need:

```python
items = client.site_explorer_organic_keywords(
    target="ahrefs.com",
    date="2025-01-15",
    select="keyword,volume,best_position",
    order_by="volume:desc",
    limit=10,
)
for item in items:
    print(item.keyword, item.volume, item.best_position)
```

### Error Handling

```python
import ahrefs

try:
    data = client.site_explorer_domain_rating(target="example.com", date="2025-01-15")
except ahrefs.AuthenticationError:    # 401
    ...
except ahrefs.RateLimitError as e:    # 429 -- e.retry_after has the delay
    ...
except ahrefs.NotFoundError:          # 404
    ...
except ahrefs.APIError as e:          # other 4xx/5xx -- e.status_code, e.response_body
    ...
except ahrefs.APIConnectionError:     # network / timeout
    ...
```

All exceptions inherit from `ahrefs.AhrefsError`.

When errors occur and the API key is valid, call `subscription_info_limits_and_usage()` to diagnose — it returns the subscription plan, key expiration date, and usage vs limits. For 403 errors specifically, also read `e.response_body` for the exact reason (units limit, export rows limit, domains-per-week limit, etc.).

### Common Parameters

Most list endpoints share these parameters:

| Parameter | Type | Description |
|-----------|------|-------------|
| `target` | `str` | Domain, URL, or path to analyze |
| `date` | `str` | Date in YYYY-MM-DD format |
| `date_from` / `date_to` | `str` | Date range for history endpoints |
| `country` | `str` | Two-letter country code (ISO 3166-1 alpha-2) |
| `select` | `str` | Comma-separated columns to return |
| `where` | `str` | Filter expression |
| `order_by` | `str` | Column and direction, e.g. `"volume:desc"` |
| `limit` | `int` | Max results to return |

Parameters typed as enums in the API reference (`CountryEnum`, `VolumeModeEnum`, etc.) accept plain strings — pass `country="us"` not `CountryEnum("us")`.

The `where` parameter takes a JSON string. Use `json.dumps()` to build it:

```python
import json
where = json.dumps({"field": "volume", "is": ["gte", 1000]})
items = client.site_explorer_organic_keywords(
    target="ahrefs.com", date="2025-01-15",
    select="keyword,volume", where=where,
)
```

For full filter syntax (boolean combinators, operators, nested fields), see `references/filter-syntax.md`.

### Recommended Defaults

Unless the user requests otherwise:

- **Backlink endpoints** (`all_backlinks`, `anchors`, `best_by_external_links`, `refdomains`): Use `history="live"` for current live data. The API defaults to `all_time` which includes lost backlinks.
- **Traffic/keyword endpoints** (`organic_keywords`, `top_pages`, `metrics`, etc.): Use today's date for the `date` parameter.

## API Methods

Use `search_api_methods("query")` or `python3 -m ahrefs.api_search "query"` to find methods by keyword. Search covers all 102 methods across 11 API sections and returns complete signatures, parameters, and response fields. Results with very large field lists (e.g. `site_audit_page_explorer` with 605 fields) are truncated at 9K chars — if you see `... [truncated]`, use `select` to request only the columns you need rather than relying on the full field list.

### Web Analytics

Web Analytics has 34 endpoints across many dimensions — not all method names match the dimension name directly (e.g. pages data uses `web_analytics_top_pages`, not `web_analytics_pages`). Always use `search_api_methods("web analytics <topic>")` to find the correct method.

These endpoints require a `project_id` (not a `target` domain). Use `from_` and `to` for datetime ranges — `from` is a Python reserved word, so the SDK uses `from_` with automatic serialization to the correct API name.

```python
# Overall traffic stats (scalar endpoint)
stats = client.web_analytics_stats(project_id=123)
print(stats.pageviews, stats.visitors, stats.visits)

# Dimension breakdown (list endpoint — use select)
browsers = client.web_analytics_browsers(
    project_id=123,
    from_="2025-01-01T00:00:00Z",
    to="2025-01-31T23:59:59Z",
    select="browser,visitors",
    limit=10,
)

# Time-series chart (list endpoint — requires granularity)
chart = client.web_analytics_chart(
    project_id=123,
    granularity="daily",
    from_="2025-01-01T00:00:00Z",
    to="2025-01-31T23:59:59Z",
)
```

### Management

Management endpoints handle Rank Tracker project configuration — creating projects, managing keyword lists, and adding competitors. Unlike other API sections, this section includes endpoints that modify state via PUT/POST/PATCH/DELETE. None of these endpoints use `select`, `where`, `order_by`, or `limit`.

- Use `management_projects()` to list all projects and find `project_id` values.
- Use `management_locations()` to get valid country codes, language codes, and location IDs before adding keywords.
- `keyword_list_id` is NOT discoverable via the API — the user must provide it from the Ahrefs web UI. Keyword list methods: `management_keyword_list_keywords` (list), `management_set_keyword_list_keywords` (add via PUT), `management_keyword_list_keywords_delete` (remove).
- **Delete endpoints are destructive and irreversible.** ALWAYS confirm with the user before calling `management_project_keywords_delete`, `management_project_competitors_delete`, or `management_keyword_list_keywords_delete`.

```python
# List all Rank Tracker projects
projects = client.management_projects()
for p in projects:
    print(p.project_id, p.project_name, p.url)

# Add keywords to a project (requires nested request types)
from ahrefs.types import ManagementSetProjectKeywordsLocation, ManagementSetProjectKeywordsKeyword

client.management_set_project_keywords(
    project_id=12345,
    locations=[ManagementSetProjectKeywordsLocation(
        country="us",
        language="en",
    )],
    keywords=[ManagementSetProjectKeywordsKeyword(keyword="ahrefs seo")],
)

# Add competitors to a project
from ahrefs.types import ManagementCreateProjectCompetitorsCompetitor

client.management_create_project_competitors(
    project_id=12345,
    competitors=[ManagementCreateProjectCompetitorsCompetitor(
        url="moz.com",
        mode="domain",
    )],
)
```
