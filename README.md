# Ahrefs API Skills

A library of skills for the [Ahrefs API](https://docs.ahrefs.com/docs/api/v3/) and [Python SDK](https://github.com/ahrefs/ahrefs-python).

## Installation

Install from this repository using `npx skills`.

```sh
# Show available skills.
npx skills add ahrefs/ahrefs-api-skills --list

# Install a specific skill.
npx skills add ahrefs/ahrefs-api-skills --skill ahrefs-python --global
```

## Skills in this repo

### ahrefs-python

Skill for developing apps with the Ahrefs Python SDK. Provides best practices for using `AhrefsClient` / `AsyncAhrefsClient`, typed request/response models, error handling, and all API sections (Site Explorer, Keywords Explorer, Rank Tracker, Site Audit, Brand Radar, SERP Overview).

```sh
npx skills add ahrefs/ahrefs-api-skills --skill ahrefs-python --global
```
