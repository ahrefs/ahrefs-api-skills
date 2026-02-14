---
name: ahrefs-python
description: Use this skill when building applications with the Ahrefs API using Python, working with SEO data (backlinks, keywords, domain ratings, organic traffic, site audits, rank tracking, brand monitoring), or needing current SDK usage patterns. Covers the ahrefs-python SDK (AhrefsClient / AsyncAhrefsClient), typed request/response models, error handling, and all API sections.
---

# Ahrefs Python SDK Skill

## Overview

The Ahrefs API provides programmatic access to Ahrefs SEO data. The official Python SDK (`ahrefs-python`) provides typed request and response models for all endpoints, auto-generated from the OpenAPI spec.

Key capabilities:
- **Site Explorer** - Backlinks, organic keywords, domain rating, traffic, referring domains
- **Keywords Explorer** - Keyword research, volumes, difficulty, related terms
- **Rank Tracker** - SERP monitoring, competitor tracking
- **Site Audit** - Technical SEO issues, page content, page explorer
- **Brand Radar** - AI brand mentions, share of voice, impressions
- **SERP Overview** - Search result analysis

## Installation

```sh
pip install git+https://github.com/ahrefs/ahrefs-python.git
```

Requires Python 3.11+. Dependencies: `httpx`, `pydantic`.

## IMPORTANT RULES

- ALWAYS use the `ahrefs-python` SDK. DO NOT make raw `httpx`/`requests` calls to the Ahrefs API.
- ALWAYS pass dates as strings in `YYYY-MM-DD` format (e.g. `"2025-01-15"`).
- ALWAYS access response data via the `.data` property, NOT by accessing the raw response fields.
- ALWAYS use `select` on list endpoints to request only the columns you need.
- USE context managers (`with` / `async with`) for client lifecycle management.
- SET the `AHREFS_API_KEY` environment variable rather than hardcoding API keys.
- The client handles retries (429, 5xx, connection errors) automatically. DO NOT implement your own retry logic on top of the SDK.

## Quick Start

```python
from ahrefs import AhrefsClient

client = AhrefsClient(api_key="your-api-key")  # or set AHREFS_API_KEY env var

response = client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")
print(response.data.domain_rating)  # 91.0
print(response.data.ahrefs_rank)    # 3
```

## SDK Patterns

### Client Setup

```python
import ahrefs

client = ahrefs.AhrefsClient(
    api_key="...",           # or set AHREFS_API_KEY env var
    base_url="...",          # override API base URL (default: https://api.ahrefs.com/v3)
    timeout=30.0,            # request timeout in seconds (default: 60)
    max_retries=3,           # retries on transient errors (default: 2)
)
```

Async client:

```python
from ahrefs import AsyncAhrefsClient

async with AsyncAhrefsClient(api_key="...") as client:
    response = await client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")
```

### Calling Methods

Two calling styles -- both are equivalent:

```python
# Keyword arguments (recommended)
response = client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")

# Request objects (full type safety)
from ahrefs.types import SiteExplorerDomainRatingRequest
request = SiteExplorerDomainRatingRequest(target="ahrefs.com", date="2025-01-15")
response = client.site_explorer_domain_rating(request)
```

Method names follow `{api_section}_{endpoint}`, e.g. `site_explorer_organic_keywords`, `keywords_explorer_overview`.

### Responses

**Scalar endpoints** -- `.data` returns a single object:

```python
response = client.site_explorer_domain_rating(target="ahrefs.com", date="2025-01-15")
print(response.data.domain_rating)
```

**List endpoints** -- `.data` returns a list. Use `select` and `limit`:

```python
response = client.site_explorer_organic_keywords(
    target="ahrefs.com",
    date="2025-01-15",
    select="keyword,volume,best_position",
    limit=10,
)
for item in response.data:
    print(item.keyword, item.volume, item.best_position)
```

### Error Handling

```python
import ahrefs

try:
    response = client.site_explorer_domain_rating(target="example.com", date="2025-01-15")
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

## API Methods

For the full list of 48 methods across 6 API sections, see `references/api-methods.md`.

All methods have full type hints and docstrings. Inspect the installed package for parameter and response field details:
- `ahrefs.types._generated` - all request/response models and enums
- `ahrefs._generated_methods` - all method signatures with docstrings
