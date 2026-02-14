# Ahrefs Python SDK - API Methods Reference

All methods are available on both `AhrefsClient` (sync) and `AsyncAhrefsClient` (async). Inspect the installed package modules `ahrefs._generated_methods` and `ahrefs.types._generated` for full parameter and response field details.

## Site Explorer (26 methods)

- `site_explorer_domain_rating()` - Domain Rating (DR) score
- `site_explorer_domain_rating_history()` - DR over time
- `site_explorer_url_rating_history()` - URL Rating over time
- `site_explorer_metrics()` - Traffic and keyword metrics
- `site_explorer_metrics_by_country()` - Metrics by country
- `site_explorer_metrics_history()` - Traffic metrics over time
- `site_explorer_organic_keywords()` - Keywords the target ranks for
- `site_explorer_organic_competitors()` - Competing domains
- `site_explorer_keywords_history()` - Organic keywords over time
- `site_explorer_total_search_volume_history()` - Total search volume over time
- `site_explorer_top_pages()` - Top pages by organic traffic
- `site_explorer_pages_by_traffic()` - Pages sorted by traffic
- `site_explorer_pages_history()` - Indexed pages over time
- `site_explorer_paid_pages()` - Pages with paid traffic
- `site_explorer_all_backlinks()` - All backlinks to target
- `site_explorer_broken_backlinks()` - Broken backlinks
- `site_explorer_backlinks_stats()` - Backlink summary stats
- `site_explorer_refdomains()` - Referring domains
- `site_explorer_refdomains_history()` - Referring domains over time
- `site_explorer_anchors()` - Anchor text distribution
- `site_explorer_linked_anchors_external()` - Outgoing anchor texts (external)
- `site_explorer_linked_anchors_internal()` - Outgoing anchor texts (internal)
- `site_explorer_linkeddomains()` - Domains linked to from target
- `site_explorer_outlinks_stats()` - Outgoing link stats
- `site_explorer_best_by_external_links()` - Pages with most external links
- `site_explorer_best_by_internal_links()` - Pages with most internal links

## Keywords Explorer (6 methods)

- `keywords_explorer_overview()` - Keyword metrics overview
- `keywords_explorer_matching_terms()` - Keyword ideas matching query
- `keywords_explorer_related_terms()` - Related keyword ideas
- `keywords_explorer_search_suggestions()` - Autocomplete suggestions
- `keywords_explorer_volume_by_country()` - Volume breakdown by country
- `keywords_explorer_volume_history()` - Historical search volume

## Rank Tracker (5 methods)

- `rank_tracker_overview()` - Tracked keyword rankings
- `rank_tracker_competitors_overview()` - Competitor visibility
- `rank_tracker_competitors_pages()` - Competitor ranking pages
- `rank_tracker_competitors_stats()` - Competitor statistics
- `rank_tracker_serp_overview()` - SERP snapshot

## Site Audit (4 methods)

- `site_audit_issues()` - Technical SEO issues
- `site_audit_page_content()` - Page HTML/content
- `site_audit_page_explorer()` - Crawled pages data
- `site_audit_projects()` - Audit projects list

## Brand Radar (6 methods)

- `brand_radar_ai_responses()` - AI-generated responses mentioning brands
- `brand_radar_impressions_history()` - Impressions over time
- `brand_radar_impressions_overview()` - Impressions summary
- `brand_radar_mentions_history()` - Mentions over time
- `brand_radar_mentions_overview()` - Mentions summary
- `brand_radar_sov_overview()` - Share of Voice

## SERP Overview (1 method)

- `serp_overview_serp_overview()` - Full SERP analysis
