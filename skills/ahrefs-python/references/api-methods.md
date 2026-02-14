# API Reference

<!-- AUTO-GENERATED -- DO NOT EDIT -->


All methods below are available on both `AhrefsClient` (sync) and
`AsyncAhrefsClient` (async). The async client uses the same method
names — just `await` the call.

---

## Brand Radar

### `brand_radar_ai_responses()`

AI Responses.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cited_domain**: The domain of a page that was used to generate the response.   type: domain  **cited_domain_subdomains**: The domain of a page that was used to generate the response. Any subdomain of the given domain will also match.   type: string  **cited_url_exact**: The URL of a page that was used to generate the response.   type: string  **cited_url_prefix**: The URL of a page that was used to generate the response. Any URL that starts with this prefix will match.   type: string  **question**: The question asked by the user.   type: string  **response** (10 units): The response from the model.   type: string  **topic**: The topic of the query.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `date` | `DateStr` | No | The date to search for in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `order_by` | `OrderByEnum` | No | The order by field. |
| `data_source` | `DataSourceEnum` | Yes | The chatbot model to use. |
| `market` | `str` | No | A comma-separated list of the niche markets of your brands. |
| `competitors` | `str` | No | A comma-separated list of competitors of your brands. |
| `brand` | `str` | No | A comma-separated list of brands to search for. At least one of brand, competitors, market or where should not be empty. |

**Returns:** `list[BrandRadarAiResponsesData]`

| Field | Type | Description |
|-------|------|-------------|
| `country` | `str` | The country of the question. |
| `links` | `list[dict[str, Any] \| None]` | (10 units) The links used for the response. |
| `question` | `str` | The question asked by the user. |
| `response` | `str` | (10 units) The response from the model. |
| `volume` | `int` | (10 units) Estimated monthly searches. This is based on our estimates for Google, combining the search volumes of rel... |

### `brand_radar_impressions_history()`

Overview history - Impressions.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cited_domain**: The domain of a page that was used to generate the response.   type: domain  **cited_domain_subdomains**: The domain of a page that was used to generate the response. Any subdomain of the given domain will also match.   type: string  **cited_url_exact**: The URL of a page that was used to generate the response.   type: string  **cited_url_prefix**: The URL of a page that was used to generate the response. Any URL that starts with this prefix will match.   type: string  **question**: The question asked by the user.   type: string  **response** (10 units): The response from the model.   type: string  **topic**: The topic of the query.   type: string |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `data_source` | `DataSourceEnum` | Yes | The chatbot model to use. |
| `market` | `str` | No | A comma-separated list of the niche markets of your brand. |
| `brand` | `str` | Yes | The brand to search for. |

**Returns:** `list[BrandRadarImpressionsHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` | date |
| `impressions` | `int` | impressions |

### `brand_radar_impressions_overview()`

Overview - Impressions.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cited_domain**: The domain of a page that was used to generate the response.   type: domain  **cited_domain_subdomains**: The domain of a page that was used to generate the response. Any subdomain of the given domain will also match.   type: string  **cited_url_exact**: The URL of a page that was used to generate the response.   type: string  **cited_url_prefix**: The URL of a page that was used to generate the response. Any URL that starts with this prefix will match.   type: string  **question**: The question asked by the user.   type: string  **response** (10 units): The response from the model.   type: string  **topic**: The topic of the query.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `data_source` | `DataSourceEnum` | Yes | The chatbot model to use. |
| `market` | `str` | No | A comma-separated list of the niche markets of your brands. |
| `competitors` | `str` | No | A comma-separated list of competitors of your brands. |
| `brand` | `str` | No | A comma-separated list of brands to search for. At least one of brand or competitors should not be empty. |

**Returns:** `list[BrandRadarImpressionsOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `brand` | `str` | Brand name (either your brand or a competitor provided in the request). |
| `no_tracked_brands` | `int` | Estimated impressions from responses related to the specified market that do not mention any provided brands (value i... |
| `only_competitors_brands` | `int` | Estimated impressions from responses mentioning only competitor brands. |
| `only_target_brand` | `int` | Estimated impressions from responses mentioning only your brand. |
| `target_and_competitors_brands` | `int` | Estimated impressions from responses mentioning both your and competitor brands. |
| `total` | `int` | Total estimated impressions for your brand (includes both `only_target_brand` and `target_and_competitors_brands`). |

### `brand_radar_mentions_history()`

Overview history - Mentions.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cited_domain**: The domain of a page that was used to generate the response.   type: domain  **cited_domain_subdomains**: The domain of a page that was used to generate the response. Any subdomain of the given domain will also match.   type: string  **cited_url_exact**: The URL of a page that was used to generate the response.   type: string  **cited_url_prefix**: The URL of a page that was used to generate the response. Any URL that starts with this prefix will match.   type: string  **question**: The question asked by the user.   type: string  **response** (10 units): The response from the model.   type: string  **topic**: The topic of the query.   type: string |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `data_source` | `DataSourceEnum` | Yes | The chatbot model to use. |
| `market` | `str` | No | A comma-separated list of the niche markets of your brand. |
| `brand` | `str` | Yes | The brand to search for. |

**Returns:** `list[BrandRadarMentionsHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` | date |
| `mentions` | `int` | mentions |

### `brand_radar_mentions_overview()`

Overview - Mentions.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cited_domain**: The domain of a page that was used to generate the response.   type: domain  **cited_domain_subdomains**: The domain of a page that was used to generate the response. Any subdomain of the given domain will also match.   type: string  **cited_url_exact**: The URL of a page that was used to generate the response.   type: string  **cited_url_prefix**: The URL of a page that was used to generate the response. Any URL that starts with this prefix will match.   type: string  **question**: The question asked by the user.   type: string  **response** (10 units): The response from the model.   type: string  **topic**: The topic of the query.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `data_source` | `DataSourceEnum` | Yes | The chatbot model to use. |
| `market` | `str` | No | A comma-separated list of the niche markets of your brands. |
| `competitors` | `str` | No | A comma-separated list of competitors of your brands. |
| `brand` | `str` | No | A comma-separated list of brands to search for. At least one of brand or competitors should not be empty. |

**Returns:** `list[BrandRadarMentionsOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `brand` | `str` | Brand name (either your brand or a competitor provided in the request). |
| `no_tracked_brands` | `int` | Estimated mentions from responses related to the specified market that do not mention any provided brands (value is z... |
| `only_competitors_brands` | `int` | Estimated mentions from responses mentioning only competitor brands. |
| `only_target_brand` | `int` | Estimated mentions from responses mentioning only your brand. |
| `target_and_competitors_brands` | `int` | Estimated mentions from responses mentioning both your and competitor brands. |
| `total` | `int` | Total estimated mentions for your brand (includes both `only_target_brand` and `target_and_competitors_brands`). |

### `brand_radar_sov_overview()`

Overview - Share of Voice.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cited_domain**: The domain of a page that was used to generate the response.   type: domain  **cited_domain_subdomains**: The domain of a page that was used to generate the response. Any subdomain of the given domain will also match.   type: string  **cited_url_exact**: The URL of a page that was used to generate the response.   type: string  **cited_url_prefix**: The URL of a page that was used to generate the response. Any URL that starts with this prefix will match.   type: string  **question**: The question asked by the user.   type: string  **response** (10 units): The response from the model.   type: string  **topic**: The topic of the query.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `data_source` | `DataSourceEnum` | Yes | The chatbot model to use. |
| `market` | `str` | No | A comma-separated list of the niche markets of your brands. |
| `competitors` | `str` | No | A comma-separated list of competitors of your brands. |
| `brand` | `str` | No | A comma-separated list of brands to search for. At least one of brand or competitors should not be empty. |

**Returns:** `list[BrandRadarSovOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `brand` | `str` | Brand name (either your brand or a competitor provided in the request). |
| `share_of_voice` | `float` | Estimated share of voice for your brand. |

---

## Keywords Explorer

### `keywords_explorer_matching_terms()`

Matching terms.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See the response schema for valid column identifiers, except for `volume_monthly`, which is not supported in `order_by` for this endpoint. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cpc**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents.   type: integer nullable  **cps**: Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search results get clicked, on average, when people search for the target keyword in a given country.   type: float nullable  **difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **first_seen**: The date when we first checked search engine results for a keyword.   type: datetime nullable  **global_volume** (10 units): How many times per month, on average, people search for the target keyword across all countries in our database.   type: integer nullable  **intents** (10 units): Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `commercial`, `transactional`, `branded` or `local`. All the fields are of type `bool`, with posible values `true` or `false`.   type: object nullable  **keyword**:    type: string  **parent_topic**: Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page instead. To identify the Parent Topic, we take the #1 ranking page for your keyword and find the keyword responsible for sending the most traffic to that page.   type: string nullable  **serp_domain_rating_top10_min**: The keyword must have at least one ranking position in the top 10 results with a DR of up to this value.   type: float nullable  **serp_domain_rating_top5_min**: The keyword must have at least one ranking position in the top 5 results with a DR of up to this value.   type: float nullable  **serp_features**: The enriched results on a search engine results page (SERP) that are not traditional organic results.   type: array(string)   enum: `"ai_overview_sitelink"` `"snippet"` `"ai_overview"` `"local_pack"` `"sitelink"` `"news"` `"image"` `"video"` `"discussion"` `"tweet"` `"paid_top"` `"paid_bottom"` `"paid_sitelink"` `"shopping"` `"knowledge_card"` `"knowledge_panel"` `"question"` `"image_th"` `"video_th"` `"organic_shopping"`  **serp_last_update**: The date when we last checked search engine results for a keyword.   type: datetime nullable  **traffic_potential** (10 units): The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords that it ranks for.   type: integer nullable  **volume** (10 units): An estimation of the average monthly number of searches for a keyword over the latest known 12 months of data.   type: integer nullable  **volume_desktop_pct**: The percentage of searches for a keyword performed on desktop devices.   type: float nullable  **volume_mobile_pct**: The percentage of searches for a keyword performed on mobile devices.   type: float nullable  **word_count**:    type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `search_engine` | `SearchEngineEnum` | No | [Deprecated on 5 Aug 2024]. |
| `keywords` | `str` | No | A comma-separated list of keywords to show metrics for. |
| `keyword_list_id` | `int` | No | The id of an existing keyword list to show metrics for. |
| `match_mode` | `MatchModeEnum` | No | Keyword ideas contain the words from your query in any order (terms mode) or in the exact order they are written (phrase mode). |
| `terms` | `TermsEnum` | No | All keywords ideas or keywords ideas phrased as questions. |

**Returns:** `list[KeywordsExplorerMatchingTermsData]`

| Field | Type | Description |
|-------|------|-------------|
| `cpc` | `int \| None` | Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, i... |
| `cps` | `float \| None` | Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search result... |
| `difficulty` | `int \| None` | (10 units) An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point ... |
| `first_seen` | `str \| None` | The date when we first checked search engine results for a keyword. |
| `global_volume` | `int \| None` | (10 units) How many times per month, on average, people search for the target keyword across all countries in our dat... |
| `intents` | `dict[str, Any] \| None` | (10 units) Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `com... |
| `keyword` | `str` |  |
| `parent_topic` | `str \| None` | Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page ins... |
| `serp_features` | `list[SerpFeaturesItemEnum \| None]` | The enriched results on a search engine results page (SERP) that are not traditional organic results. |
| `serp_last_update` | `str \| None` | The date when we last checked search engine results for a keyword. |
| `traffic_potential` | `int \| None` | (10 units) The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords... |
| `volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for a keyword over the latest known 12 months of d... |
| `volume_desktop_pct` | `float \| None` | The percentage of searches for a keyword performed on desktop devices. |
| `volume_mobile_pct` | `float \| None` | The percentage of searches for a keyword performed on mobile devices. |
| `volume_monthly` | `int \| None` | (10 units) An estimation of the number of searches for a keyword over the latest month. This field may not be include... |

### `keywords_explorer_overview()`

Overview.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **clicks**: The average monthly number of clicks on the search results that people make while searching for the target keyword.   type: integer nullable  **cpc**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents.   type: integer nullable  **cps**: Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search results get clicked, on average, when people search for the target keyword in a given country.   type: float nullable  **difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **first_seen**: The date when we first checked search engine results for a keyword.   type: datetime nullable  **global_volume** (10 units): How many times per month, on average, people search for the target keyword across all countries in our database.   type: integer nullable  **intents** (10 units): Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `commercial`, `transactional`, `branded` or `local`. All the fields are of type `bool`, with posible values `true` or `false`.   type: object nullable  **keyword**:    type: string  **parent_topic**: Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page instead. To identify the Parent Topic, we take the #1 ranking page for your keyword and find the keyword responsible for sending the most traffic to that page.   type: string nullable  **parent_volume** (10 units): The search volume of the parent topic.   type: integer nullable  **serp_domain_rating_top10_min**: The keyword must have at least one ranking position in the top 10 results with a DR of up to this value.   type: float nullable  **serp_domain_rating_top5_min**: The keyword must have at least one ranking position in the top 5 results with a DR of up to this value.   type: float nullable  **serp_features**: The enriched results on a search engine results page (SERP) that are not traditional organic results.   type: array(string)   enum: `"ai_overview_sitelink"` `"snippet"` `"ai_overview"` `"local_pack"` `"sitelink"` `"news"` `"image"` `"video"` `"discussion"` `"tweet"` `"paid_top"` `"paid_bottom"` `"paid_sitelink"` `"shopping"` `"knowledge_card"` `"knowledge_panel"` `"question"` `"image_th"` `"video_th"` `"organic_shopping"`  **serp_last_update**: The date when we last checked search engine results for a keyword.   type: datetime nullable  **traffic_potential** (10 units): The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords that it ranks for.   type: integer nullable  **volume** (10 units): An estimation of the average monthly number of searches for a keyword over the latest known 12 months of data.   type: integer nullable  **volume_desktop_pct**: The percentage of searches for a keyword performed on desktop devices.   type: float nullable  **volume_mobile_pct**: The percentage of searches for a keyword performed on mobile devices.   type: float nullable  **word_count**:    type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `volume_monthly_date_to` | `DateStr` | No | The end date in YYYY-MM-DD format for retrieving historical monthly search volumes in the `volume_monthly_history` field. Required only if `volume_monthly_history` is requested. |
| `volume_monthly_date_from` | `DateStr` | No | The start date in YYYY-MM-DD format for retrieving historical monthly search volumes in the `volume_monthly_history` field. Required only if `volume_monthly_history` is requested. |
| `target_mode` | `ModeEnum` | No | The scope of the target URL you specified. |
| `target` | `str` | No | The target of the search: a domain or a URL. |
| `target_position` | `TargetPositionEnum` | No | Filters keywords based on the ranking position of the specified `target`. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `search_engine` | `SearchEngineEnum` | No | [Deprecated on 5 Aug 2024]. |
| `keywords` | `str` | No | A comma-separated list of keywords to show metrics for. |
| `keyword_list_id` | `int` | No | The id of an existing keyword list to show metrics for. |

**Returns:** `list[KeywordsExplorerOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `clicks` | `int \| None` | The average monthly number of clicks on the search results that people make while searching for the target keyword. |
| `cpc` | `int \| None` | Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, i... |
| `cps` | `float \| None` | Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search result... |
| `difficulty` | `int \| None` | (10 units) An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point ... |
| `first_seen` | `str \| None` | The date when we first checked search engine results for a keyword. |
| `global_volume` | `int \| None` | (10 units) How many times per month, on average, people search for the target keyword across all countries in our dat... |
| `intents` | `dict[str, Any] \| None` | (10 units) Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `com... |
| `keyword` | `str` |  |
| `parent_topic` | `str \| None` | Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page ins... |
| `parent_volume` | `int \| None` | (10 units) The search volume of the parent topic. |
| `searches_pct_clicks_organic_and_paid` | `float \| None` | The average monthly percentage of people who clicked on both organic and paid results while searching for the target ... |
| `searches_pct_clicks_organic_only` | `float \| None` | The average monthly percentage of people who clicked only on organic results while searching for the target keyword. |
| `searches_pct_clicks_paid_only` | `float \| None` | The average monthly percentage of people who clicked only on paid results while searching for the target keyword. |
| `serp_features` | `list[SerpFeaturesItemEnum \| None]` | The enriched results on a search engine results page (SERP) that are not traditional organic results. |
| `serp_last_update` | `str \| None` | The date when we last checked search engine results for a keyword. |
| `traffic_potential` | `int \| None` | (10 units) The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords... |
| `volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for a keyword over the latest known 12 months of d... |
| `volume_desktop_pct` | `float \| None` | The percentage of searches for a keyword performed on desktop devices. |
| `volume_mobile_pct` | `float \| None` | The percentage of searches for a keyword performed on mobile devices. |
| `volume_monthly` | `int \| None` | (10 units) An estimation of the number of searches for a keyword over the latest month. This field may not be include... |
| `volume_monthly_history` | `list[dict[str, Any] \| None]` | (2 units per historical month, with a minimum of 50 units) Historical monthly search volume estimates of a keyword fo... |

### `keywords_explorer_related_terms()`

Related terms.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See the response schema for valid column identifiers, except for `volume_monthly`, which is not supported in `order_by` for this endpoint. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cpc**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents.   type: integer nullable  **cps**: Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search results get clicked, on average, when people search for the target keyword in a given country.   type: float nullable  **difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **first_seen**: The date when we first checked search engine results for a keyword.   type: datetime nullable  **global_volume** (10 units): How many times per month, on average, people search for the target keyword across all countries in our database.   type: integer nullable  **intents** (10 units): Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `commercial`, `transactional`, `branded` or `local`. All the fields are of type `bool`, with posible values `true` or `false`.   type: object nullable  **keyword**:    type: string  **parent_topic**: Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page instead. To identify the Parent Topic, we take the #1 ranking page for your keyword and find the keyword responsible for sending the most traffic to that page.   type: string nullable  **serp_domain_rating_top10_min**: The keyword must have at least one ranking position in the top 10 results with a DR of up to this value.   type: float nullable  **serp_domain_rating_top5_min**: The keyword must have at least one ranking position in the top 5 results with a DR of up to this value.   type: float nullable  **serp_features**: The enriched results on a search engine results page (SERP) that are not traditional organic results.   type: array(string)   enum: `"ai_overview_sitelink"` `"snippet"` `"ai_overview"` `"local_pack"` `"sitelink"` `"news"` `"image"` `"video"` `"discussion"` `"tweet"` `"paid_top"` `"paid_bottom"` `"paid_sitelink"` `"shopping"` `"knowledge_card"` `"knowledge_panel"` `"question"` `"image_th"` `"video_th"` `"organic_shopping"`  **serp_last_update**: The date when we last checked search engine results for a keyword.   type: datetime nullable  **traffic_potential** (10 units): The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords that it ranks for.   type: integer nullable  **volume** (10 units): An estimation of the average monthly number of searches for a keyword over the latest known 12 months of data.   type: integer nullable  **volume_desktop_pct**: The percentage of searches for a keyword performed on desktop devices.   type: float nullable  **volume_mobile_pct**: The percentage of searches for a keyword performed on mobile devices.   type: float nullable  **word_count**:    type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `keywords` | `str` | No | A comma-separated list of keywords to show metrics for. |
| `keyword_list_id` | `int` | No | The id of an existing keyword list to show metrics for. |
| `view_for` | `ViewForEnum` | No | View keywords for the top 10 or top 100 ranking pages. |
| `terms` | `TermsEnum1` | No | Related keywords which top-ranking pages also rank for (`also_rank_for`), additional keywords frequently mentioned in top-ranking pages (`also_talk_about`), or combination of both (`all`). |

**Returns:** `list[KeywordsExplorerRelatedTermsData]`

| Field | Type | Description |
|-------|------|-------------|
| `cpc` | `int \| None` | Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, i... |
| `cps` | `float \| None` | Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search result... |
| `difficulty` | `int \| None` | (10 units) An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point ... |
| `first_seen` | `str \| None` | The date when we first checked search engine results for a keyword. |
| `global_volume` | `int \| None` | (10 units) How many times per month, on average, people search for the target keyword across all countries in our dat... |
| `intents` | `dict[str, Any] \| None` | (10 units) Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `com... |
| `keyword` | `str` |  |
| `parent_topic` | `str \| None` | Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page ins... |
| `serp_features` | `list[SerpFeaturesItemEnum \| None]` | The enriched results on a search engine results page (SERP) that are not traditional organic results. |
| `serp_last_update` | `str \| None` | The date when we last checked search engine results for a keyword. |
| `traffic_potential` | `int \| None` | (10 units) The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords... |
| `volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for a keyword over the latest known 12 months of d... |
| `volume_desktop_pct` | `float \| None` | The percentage of searches for a keyword performed on desktop devices. |
| `volume_mobile_pct` | `float \| None` | The percentage of searches for a keyword performed on mobile devices. |
| `volume_monthly` | `int \| None` | (10 units) An estimation of the number of searches for a keyword over the latest month. This field may not be include... |

### `keywords_explorer_search_suggestions()`

Search suggestions.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See the response schema for valid column identifiers, except for `volume_monthly`, which is not supported in `order_by` for this endpoint. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cpc**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents.   type: integer nullable  **cps**: Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search results get clicked, on average, when people search for the target keyword in a given country.   type: float nullable  **difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **first_seen**: The date when we first checked search engine results for a keyword.   type: datetime nullable  **global_volume** (10 units): How many times per month, on average, people search for the target keyword across all countries in our database.   type: integer nullable  **intents** (10 units): Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `commercial`, `transactional`, `branded` or `local`. All the fields are of type `bool`, with posible values `true` or `false`.   type: object nullable  **keyword**:    type: string  **parent_topic**: Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page instead. To identify the Parent Topic, we take the #1 ranking page for your keyword and find the keyword responsible for sending the most traffic to that page.   type: string nullable  **serp_domain_rating_top10_min**: The keyword must have at least one ranking position in the top 10 results with a DR of up to this value.   type: float nullable  **serp_domain_rating_top5_min**: The keyword must have at least one ranking position in the top 5 results with a DR of up to this value.   type: float nullable  **serp_features**: The enriched results on a search engine results page (SERP) that are not traditional organic results.   type: array(string)   enum: `"ai_overview_sitelink"` `"snippet"` `"ai_overview"` `"local_pack"` `"sitelink"` `"news"` `"image"` `"video"` `"discussion"` `"tweet"` `"paid_top"` `"paid_bottom"` `"paid_sitelink"` `"shopping"` `"knowledge_card"` `"knowledge_panel"` `"question"` `"image_th"` `"video_th"` `"organic_shopping"`  **serp_last_update**: The date when we last checked search engine results for a keyword.   type: datetime nullable  **traffic_potential** (10 units): The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords that it ranks for.   type: integer nullable  **volume** (10 units): An estimation of the average monthly number of searches for a keyword over the latest known 12 months of data.   type: integer nullable  **volume_desktop_pct**: The percentage of searches for a keyword performed on desktop devices.   type: float nullable  **volume_mobile_pct**: The percentage of searches for a keyword performed on mobile devices.   type: float nullable  **word_count**:    type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `search_engine` | `SearchEngineEnum` | No | [Deprecated on 5 Aug 2024]. |
| `keywords` | `str` | No | A comma-separated list of keywords to show metrics for. |
| `keyword_list_id` | `int` | No | The id of an existing keyword list to show metrics for. |

**Returns:** `list[KeywordsExplorerSearchSuggestionsData]`

| Field | Type | Description |
|-------|------|-------------|
| `cpc` | `int \| None` | Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, i... |
| `cps` | `float \| None` | Clicks Per Search (or CPS) is the ratio of Clicks to Keyword Search volume. It shows how many different search result... |
| `difficulty` | `int \| None` | (10 units) An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point ... |
| `first_seen` | `str \| None` | The date when we first checked search engine results for a keyword. |
| `global_volume` | `int \| None` | (10 units) How many times per month, on average, people search for the target keyword across all countries in our dat... |
| `intents` | `dict[str, Any] \| None` | (10 units) Indicates the purpose behind the user's search query. Object fields: `informational`, `navigational`, `com... |
| `keyword` | `str` |  |
| `parent_topic` | `str \| None` | Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page ins... |
| `serp_features` | `list[SerpFeaturesItemEnum \| None]` | The enriched results on a search engine results page (SERP) that are not traditional organic results. |
| `serp_last_update` | `str \| None` | The date when we last checked search engine results for a keyword. |
| `traffic_potential` | `int \| None` | (10 units) The sum of organic traffic that the #1 ranking page for your target keyword receives from all the keywords... |
| `volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for a keyword over the latest known 12 months of d... |
| `volume_desktop_pct` | `float \| None` | The percentage of searches for a keyword performed on desktop devices. |
| `volume_mobile_pct` | `float \| None` | The percentage of searches for a keyword performed on mobile devices. |
| `volume_monthly` | `int \| None` | (10 units) An estimation of the number of searches for a keyword over the latest month. This field may not be include... |

### `keywords_explorer_volume_by_country()`

Volume by country.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `limit` | `int` | No | The number of results to return. |
| `search_engine` | `SearchEngineEnum` | No | [Deprecated on 5 Aug 2024]. |
| `keyword` | `str` | Yes | The keyword to show metrics for. |

**Returns:** `list[KeywordsExplorerVolumeByCountryData]`

| Field | Type | Description |
|-------|------|-------------|
| `country` | `str` |  |
| `volume` | `int` | (10 units) An estimation of the average monthly number of searches for a keyword in a given country. |

### `keywords_explorer_volume_history()`

Volume history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | No | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `keyword` | `str` | Yes | The keyword to show metrics for. |

**Returns:** `list[KeywordsExplorerVolumeHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `volume` | `int` | An estimation of the number of searches for a keyword over a given month. |

---

## Rank Tracker

### `rank_tracker_competitors_overview()`

Competitors overview.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **country**: The country that a given keyword is being tracked in. A two-letter country code (ISO 3166-1 alpha-2).   type: string   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **is_main_position**: Excludes positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter).   type: boolean  **is_main_position_prev**: Excludes positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter) on the comparison date.   type: boolean  **keyword**: The keyword your target ranks for.   type: string  **keyword_difficulty**: An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **keyword_has_data**: Will return `false` if the keyword is still processing and no SERP has been fetched yet.   type: boolean  **keyword_is_frozen**: Indicates whether a keyword has exceeded the tracked keywords limit on your plan. Such keywords are "frozen", meaning they do not have their rankings updated.   type: boolean  **language**: The SERP language that a given keyword is being tracked for.   type: string  **location**: The location (country, state/province, or city) that a given keyword is being tracked in.   type: string  **serp_features**: The SERP features that appear in search results for a keyword.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_updated**: The date when we last checked search engine results for a keyword.   type: datetime nullable  **serp_updated_prev**: The date when we checked search engine results up to the comparison date.   type: datetime nullable  **tags**: A list of tags assigned to a given keyword.   type: array(string)  **volume**: An estimation of the average monthly number of searches for a keyword over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `device` | `DeviceEnum` | Yes | Choose between mobile and desktop rankings. |
| `project_id` | `int` | Yes | The unique identifier of the project. You can find it in the URL of your Rank Tracker project in Ahrefs: `https://app.ahrefs.com/rank-tracker/overview/#project_id#` |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[RankTrackerCompetitorsOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `competitors_list` | `list[dict[str, Any] \| None]` | Competitors information for a given keyword. The following fields are included: `url`, `url_prev`, `position`, `posit... |
| `country` | `CountryEnum1` | The country that a given keyword is being tracked in. A two-letter country code (ISO 3166-1 alpha-2). |
| `keyword` | `str` | The keyword your target ranks for. |
| `keyword_difficulty` | `int \| None` | An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale. |
| `keyword_has_data` | `bool` | Will return `false` if the keyword is still processing and no SERP has been fetched yet. |
| `keyword_is_frozen` | `bool` | Indicates whether a keyword has exceeded the tracked keywords limit on your plan. Such keywords are "frozen", meaning... |
| `language` | `str` | The SERP language that a given keyword is being tracked for. |
| `location` | `str` | The location (country, state/province, or city) that a given keyword is being tracked in. |
| `serp_features` | `list[SerpFeaturesItemEnum1 \| None]` | The SERP features that appear in search results for a keyword. |
| `serp_updated` | `str \| None` | The date when we last checked search engine results for a keyword. |
| `serp_updated_prev` | `str \| None` | The date when we checked search engine results up to the comparison date. |
| `tags` | `list[str \| None]` | A list of tags assigned to a given keyword. |
| `volume` | `int \| None` | An estimation of the average monthly number of searches for a keyword over the latest month or over the latest known ... |

### `rank_tracker_competitors_pages()`

Competitors pages.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **country**: The country that a given keyword is being tracked in. A two-letter country code (ISO 3166-1 alpha-2).   type: string   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **country_prev**: The country that a given keyword is being tracked in on the comparison date. A two-letter country code (ISO 3166-1 alpha-2).   type: string   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **domain**: The page domain.   type: string  **language**: The SERP language that a given keyword is being tracked for.   type: string  **language_prev**: The SERP language on the comparison date.   type: string  **location**: The location (country, state/province, or city) that a given keyword is being tracked in.   type: string  **location_prev**: The location (country, state/province, or city) that a given keyword is being tracked in on the comparison date.   type: string  **tags**: A list of tags assigned to a given keyword.   type: array(string)  **tags_prev**: A list of tags assigned to a given keyword on the comparison date.   type: array(string)  **url**: The page URL.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `target_and_tracked_competitors_only` | `bool` | No | Restrict pages to target and tracked competitors |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `device` | `DeviceEnum` | Yes | Choose between mobile and desktop rankings. |
| `project_id` | `int` | Yes | The unique identifier of the project. You can find it in the URL of your Rank Tracker project in Ahrefs: `https://app.ahrefs.com/rank-tracker/overview/#project_id#` |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[RankTrackerCompetitorsPagesData]`

| Field | Type | Description |
|-------|------|-------------|
| `keywords` | `int` | The total number of keywords that your target ranks for in the top 100 organic search results. |
| `share_of_traffic_value` | `float` | The share of your target's organic search traffic value compared to the total organic search traffic value for all tr... |
| `share_of_traffic_value_prev` | `float` | The share of traffic value on the comparison date. |
| `share_of_voice` | `float` | The share of your target's organic search traffic compared to the total organic search traffic for all tracked keywords. |
| `share_of_voice_prev` | `float` | The share of voice on the comparison date. |
| `status` | `StatusEnum` | The status of a page: the new page that just started to rank ("left"), the lost page that disappeared from search res... |
| `title` | `str \| None` | The title displayed for the page in its top keyword's SERP. |
| `title_prev` | `str \| None` | The title on the comparison date. |
| `traffic` | `int` | An estimation of the number of monthly visits that a page gets from organic search. |
| `traffic_prev` | `int` | The traffic on the comparison date. |
| `traffic_value` | `int \| None` | The estimated value of a page’s monthly organic search traffic, in USD cents. |
| `traffic_value_prev` | `int \| None` | The traffic value on the comparison date. |
| `url` | `str` | The page URL. |

### `rank_tracker_competitors_stats()`

Competitors metrics.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `device` | `DeviceEnum` | Yes | Choose between mobile and desktop rankings. |
| `project_id` | `int` | Yes | The unique identifier of the project. You can find it in the URL of your Rank Tracker project in Ahrefs: `https://app.ahrefs.com/rank-tracker/overview/#project_id#` |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[RankTrackerCompetitorsStatsData]`

| Field | Type | Description |
|-------|------|-------------|
| `ai_overview_count` | `int` | The total number of tracked keywords for which your target ranks in an AI Overview. |
| `average_position` | `float \| None` | The average of your target's top organic positions across all tracked keywords. |
| `competitor` | `str` | Competitor's URL. |
| `discussions_count` | `int` | The total number of tracked keywords for which your target ranks in Discussions and forums. |
| `featured_snippet_count` | `int` | The total number of tracked keywords for which your target ranks in a Featured snippet. |
| `image_pack_count` | `int` | The total number of tracked keywords for which your target ranks in an Image pack. |
| `knowledge_card_count` | `int` | The total number of tracked keywords for which your target ranks in a Knowledge card. |
| `knowledge_panel_count` | `int` | The total number of tracked keywords for which your target ranks in a Knowledge panel. |
| `pos_11_20` | `int` | The total number of tracked keywords for which your target's top organic position is within the 11th to 20th results. |
| `pos_1_3` | `int` | The total number of tracked keywords for which your target's top organic position is within the top 3 results. |
| `pos_21_50` | `int` | The total number of tracked keywords for which your target's top organic position is within the 21st to 50th results. |
| `pos_4_10` | `int` | The total number of tracked keywords for which your target's top organic position is within the 4th to 10th results. |
| `pos_51_plus` | `int` | The total number of tracked keywords for which your target's top organic position is the 51st or higher. |
| `pos_no_rank` | `int` | The total number of tracked keywords where your target doesn't rank. |
| `share_of_traffic_value` | `float` | The share of your target's organic search traffic value compared to the total organic search traffic value for all tr... |
| `share_of_voice` | `float` | The share of your target's organic search traffic compared to the total organic search traffic for all tracked keywords. |
| `sitelinks_count` | `int` | The total number of tracked keywords for which your target ranks in Sitelinks. |
| `thumbnail_count` | `int` | The total number of tracked keywords for which your target ranks in a Thumbnail. |
| `top_stories_count` | `int` | The total number of tracked keywords for which your target ranks in Top stories. |
| `traffic` | `int \| None` | The estimated number of monthly visits that your target gets from organic search for all tracked keywords. |
| `traffic_value` | `int \| None` | The estimated value of your target's monthly organic search traffic for all tracked keywords. |
| `video_preview_count` | `int` | The total number of tracked keywords for which your target ranks in a Video preview. |
| `videos_count` | `int` | The total number of tracked keywords for which your target ranks in Videos. |
| `x_count` | `int` | The total number of tracked keywords for which your target ranks in an X (Twitter) widget. |

### `rank_tracker_overview()`

Overview.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **best_position_has_thumbnail**: The top position (or target URL’s, if set) has a thumbnail.   type: boolean nullable  **best_position_has_thumbnail_previous**: The top position (or target URL’s, if set) has a thumbnail on the comparison date.   type: boolean nullable  **best_position_has_video_preview**: The top position (or target URL’s, if set) has a video preview.   type: boolean nullable  **best_position_has_video_preview_previous**: The top position (or target URL’s, if set) has a video preview on the comparison date.   type: boolean nullable  **best_position_kind**: The kind of top position (or target URL’s, if set): organic, paid, or a SERP feature.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **best_position_kind_previous**: The kind of top position (or target URL’s, if set) on the comparison date.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **clicks**: Clicks metric refers to the average monthly number of clicks on the search results that people make while searching for the target keyword. Some searches generate clicks on multiple results, while others might not end in any clicks at all.   type: integer nullable  **clicks_per_search**: Clicks Per Search is the ratio of Clicks to Keyword Search volume. It shows how many different search results get clicked, on average, when people search for the target keyword in a given country.   type: float nullable  **cost_per_click**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword.   type: integer nullable  **country**: The country that a given keyword is being tracked in. A two-letter country code (ISO 3166-1 alpha-2).   type: string   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **country_prev**: The country that a given keyword is being tracked in on the comparison date. A two-letter country code (ISO 3166-1 alpha-2).   type: string   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **created_at**: The date when a keyword was added to the project.   type: datetime  **is_branded**: User intent: branded. The user is searching for a specific brand or company name.   type: boolean  **is_commercial**: User intent: commercial. The user is comparing products or services before making a purchase decision.   type: boolean  **is_informational**: User intent: informational. The user is looking for information or an answer to a specific question.   type: boolean  **is_local**: User intent: local. The user is looking for information relevant to a specific location or nearby services.   type: boolean  **is_main_position**: Excludes positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter).   type: boolean  **is_main_position_prev**: Excludes positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter) on the comparison date.   type: boolean  **is_navigational**: User intent: navigational. The user is searching for a specific website or web page.   type: boolean  **is_transactional**: User intent: transactional. The user is ready to complete an action, often a purchase.   type: boolean  **keyword**: The keyword your target ranks for.   type: string  **keyword_difficulty**: An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **keyword_has_data**: Will return `false` if the keyword is still processing and no SERP has been fetched yet.   type: boolean  **keyword_is_frozen**: Indicates whether a keyword has exceeded the tracked keywords limit on your plan. Such keywords are "frozen", meaning they do not have their rankings updated.   type: boolean  **keyword_prev**: The keyword your target ranks for on the comparison date.   type: string  **keyword_words**: The number of words in a keyword.   type: integer  **keyword_words_prev**: The number of words in a keyword on the comparison date.   type: integer  **language**: The SERP language that a given keyword is being tracked for.   type: string  **language_prev**: The SERP language on the comparison date.   type: string  **location**: The location (country, state/province, or city) that a given keyword is being tracked in.   type: string  **location_prev**: The location (country, state/province, or city) that a given keyword is being tracked in on the comparison date.   type: string  **parent_topic**: Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page instead.  To identify the Parent Topic, we take the #1 ranking page for your keyword and find the keyword responsible for sending the most traffic to that page.   type: string nullable  **position**: The top position (or target URL’s, if set) in organic search.   type: integer nullable  **position_diff**: The change in top position (or target URL’s, if set) between selected dates.   type: integer nullable  **position_prev**: The top position (or target URL’s, if set) on the comparison date.   type: integer nullable  **search_type_image**: Search type Image shows the percentage of searches for a keyword made for images, highlighting interest in visual content.   type: float nullable  **search_type_news**: Search type News shows the percentage of searches for a keyword made for news articles.   type: float nullable  **search_type_video**: Search type Video shows the percentage of searches for a keyword made for video, reflecting interest in video content.   type: float nullable  **search_type_web**: Search type Web shows the percentage of searches for a keyword made for general web content, indicating interest in a wide range of information.   type: float nullable  **serp_features**: The SERP features that appear in search results for a keyword.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_features_prev**: The SERP features that appear in search results for a keyword on the comparison date.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_updated**: The date when we last checked search engine results for a keyword.   type: datetime nullable  **serp_updated_prev**: The date when we checked search engine results up to the comparison date.   type: datetime nullable  **tags**: A list of tags assigned to a given keyword.   type: array(string)  **tags_prev**: A list of tags assigned to a given keyword on the comparison date.   type: array(string)  **target_positions_count**: The number of target URLs ranking for a keyword.   type: integer  **traffic**: An estimation of the number of monthly visits that a page gets from organic search over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable  **traffic_diff**: The change in traffic between your selected dates.   type: integer nullable  **traffic_prev**: An estimation of the number of monthly visits that a page gets from organic search over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable  **url**: The top-ranking URL (or target URL, if set) in organic search.   type: string nullable  **url_prev**: The top-ranking URL (or target URL, if set) on the comparison date.   type: string nullable  **volume**: An estimation of the average monthly number of searches for a keyword over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable  **volume_desktop_pct**: The percentage of the total search volume that comes from desktop devices.   type: float nullable  **volume_mobile_pct**: The percentage of the total search volume that comes from mobile devices.   type: float nullable |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `device` | `DeviceEnum` | Yes | Choose between mobile and desktop rankings. |
| `project_id` | `int` | Yes | The unique identifier of the project. You can find it in the URL of your Rank Tracker project in Ahrefs: `https://app.ahrefs.com/rank-tracker/overview/#project_id#` |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[RankTrackerOverviewData]`

<details>
<summary>50 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `best_position_has_thumbnail` | `bool \| None` | The top position (or target URL’s, if set) has a thumbnail. |
| `best_position_has_thumbnail_previous` | `bool \| None` | The top position (or target URL’s, if set) has a thumbnail on the comparison date. |
| `best_position_has_video_preview` | `bool \| None` | The top position (or target URL’s, if set) has a video preview. |
| `best_position_has_video_preview_previous` | `bool \| None` | The top position (or target URL’s, if set) has a video preview on the comparison date. |
| `best_position_kind` | `BestPositionKindEnum \| None` | The kind of top position (or target URL’s, if set): organic, paid, or a SERP feature. |
| `best_position_kind_previous` | `BestPositionKindEnum \| None` | The kind of top position (or target URL’s, if set) on the comparison date. |
| `clicks` | `int \| None` | Clicks metric refers to the average monthly number of clicks on the search results that people make while searching f... |
| `clicks_per_search` | `float \| None` | Clicks Per Search is the ratio of Clicks to Keyword Search volume. It shows how many different search results get cli... |
| `cost_per_click` | `int \| None` | Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword. |
| `country` | `CountryEnum1` | The country that a given keyword is being tracked in. A two-letter country code (ISO 3166-1 alpha-2). |
| `country_prev` | `CountryEnum1` | The country that a given keyword is being tracked in on the comparison date. A two-letter country code (ISO 3166-1 al... |
| `created_at` | `str` | The date when a keyword was added to the project. |
| `is_branded` | `bool` | User intent: branded. The user is searching for a specific brand or company name. |
| `is_commercial` | `bool` | User intent: commercial. The user is comparing products or services before making a purchase decision. |
| `is_informational` | `bool` | User intent: informational. The user is looking for information or an answer to a specific question. |
| `is_local` | `bool` | User intent: local. The user is looking for information relevant to a specific location or nearby services. |
| `is_navigational` | `bool` | User intent: navigational. The user is searching for a specific website or web page. |
| `is_transactional` | `bool` | User intent: transactional. The user is ready to complete an action, often a purchase. |
| `keyword` | `str` | The keyword your target ranks for. |
| `keyword_difficulty` | `int \| None` | An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale. |
| `keyword_has_data` | `bool` | Will return `false` if the keyword is still processing and no SERP has been fetched yet. |
| `keyword_is_frozen` | `bool` | Indicates whether a keyword has exceeded the tracked keywords limit on your plan. Such keywords are "frozen", meaning... |
| `keyword_prev` | `str` | The keyword your target ranks for on the comparison date. |
| `language` | `str` | The SERP language that a given keyword is being tracked for. |
| `language_prev` | `str` | The SERP language on the comparison date. |
| `location` | `str` | The location (country, state/province, or city) that a given keyword is being tracked in. |
| `location_prev` | `str` | The location (country, state/province, or city) that a given keyword is being tracked in on the comparison date. |
| `parent_topic` | `str \| None` | Parent Topic determines if you can rank for your target keyword while targeting a more general topic on your page ins... |
| `position` | `int \| None` | The top position (or target URL’s, if set) in organic search. |
| `position_diff` | `int \| None` | The change in top position (or target URL’s, if set) between selected dates. |
| `position_prev` | `int \| None` | The top position (or target URL’s, if set) on the comparison date. |
| `search_type_image` | `float \| None` | Search type Image shows the percentage of searches for a keyword made for images, highlighting interest in visual con... |
| `search_type_news` | `float \| None` | Search type News shows the percentage of searches for a keyword made for news articles. |
| `search_type_video` | `float \| None` | Search type Video shows the percentage of searches for a keyword made for video, reflecting interest in video content. |
| `search_type_web` | `float \| None` | Search type Web shows the percentage of searches for a keyword made for general web content, indicating interest in a... |
| `serp_features` | `list[SerpFeaturesItemEnum1 \| None]` | The SERP features that appear in search results for a keyword. |
| `serp_features_prev` | `list[SerpFeaturesItemEnum1 \| None]` | The SERP features that appear in search results for a keyword on the comparison date. |
| `serp_updated` | `str \| None` | The date when we last checked search engine results for a keyword. |
| `serp_updated_prev` | `str \| None` | The date when we checked search engine results up to the comparison date. |
| `tags` | `list[str \| None]` | A list of tags assigned to a given keyword. |
| `tags_prev` | `list[str \| None]` | A list of tags assigned to a given keyword on the comparison date. |
| `target_positions_count` | `int` | The number of target URLs ranking for a keyword. |
| `traffic` | `int \| None` | An estimation of the number of monthly visits that a page gets from organic search over the latest month or over the ... |
| `traffic_diff` | `int \| None` | The change in traffic between your selected dates. |
| `traffic_prev` | `int \| None` | An estimation of the number of monthly visits that a page gets from organic search over the latest month or over the ... |
| `url` | `str \| None` | The top-ranking URL (or target URL, if set) in organic search. |
| `url_prev` | `str \| None` | The top-ranking URL (or target URL, if set) on the comparison date. |
| `volume` | `int \| None` | An estimation of the average monthly number of searches for a keyword over the latest month or over the latest known ... |
| `volume_desktop_pct` | `float \| None` | The percentage of the total search volume that comes from desktop devices. |
| `volume_mobile_pct` | `float \| None` | The percentage of the total search volume that comes from mobile devices. |

</details>

### `rank_tracker_serp_overview()`

SERP Overview.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `top_positions` | `int` | No | The number of top organic SERP positions to return. If not specified, all available positions will be returned. |
| `device` | `DeviceEnum` | Yes | Choose between mobile and desktop rankings. |
| `date` | `str` | No | A timestamp on which the last available SERP Overview is returned in YYYY-MM-DDThh:mm:ss format. If it is not specified, the most recent SERP Overview is returned. |
| `location_id` | `int` | No | The location ID of a tracked keyword.You can use the `management/project-keywords` endpoint to get country codes, language codes and location IDs for your tracked keywords. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `language_code` | `str` | No | The language code of a tracked keyword.You can use the `management/project-keywords` endpoint to get country codes, language codes and location IDs for your tracked keywords. |
| `keyword` | `str` | Yes | The keyword to return SERP Overview for. |
| `project_id` | `int` | Yes | The unique identifier of the project. You can find it in the URL of your Rank Tracker project in Ahrefs: `https://app.ahrefs.com/rank-tracker/overview/#project_id#` |

**Returns:** `list[RankTrackerSerpOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `position` | `int` | The position of the search result in SERP. |
| `title` | `str \| None` | The title of a ranking page. |
| `url` | `str \| None` | The URL of a ranking page. |
| `type` | `list[str \| None]` | The kind of the position: organic, paid, or a SERP feature. Allowed values: `ai_overview`, `ai_overview_sitelink`, `d... |
| `update_date` | `str` | The date when we checked search engine results for a keyword. |
| `nr_words` | `int \| None` | The total number of words present in the HTML of a web page. |
| `domain_rating` | `float \| None` | The strength of a domain’s backlink profile compared to the others in our database on a 100-point scale. |
| `url_rating` | `float \| None` | The strength of a page's backlink profile on a 100-point logarithmic scale. |
| `ahrefs_rank` | `int \| None` | The strength of a domain's backlink profile compared to the other websites in our database, with rank #1 being the st... |
| `backlinks` | `int \| None` | The total number of links from other websites pointing to a search result. |
| `refdomains` | `int \| None` | The total number of unique domains linking to a search result. |
| `traffic` | `int \| None` | An estimation of the monthly organic search traffic that a result gets from all the keywords that it ranks for. |
| `value` | `int \| None` | The estimated value of a page’s monthly organic search traffic, in USD cents. |
| `keywords` | `int \| None` | The total number of keywords that a search result ranks for in the top 100 organic positions. |
| `top_keyword` | `str \| None` | The keyword that brings the most organic traffic to a search result. |
| `top_keyword_volume` | `int \| None` | An estimation of the average monthly number of searches for the top keyword over the latest known 12 months of data. |

---

## Serp Overview

### `serp_overview_serp_overview()`

SERP Overview.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `top_positions` | `int` | No | The number of top organic SERP positions to return. If not specified, all available positions will be returned. |
| `date` | `str` | No | A timestamp on which the last available SERP Overview is returned in YYYY-MM-DDThh:mm:ss format. If it is not specified, the most recent SERP Overview is returned. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `keyword` | `str` | Yes | The keyword to return SERP Overview for. |

**Returns:** `list[SerpOverviewSerpOverviewData]`

| Field | Type | Description |
|-------|------|-------------|
| `ahrefs_rank` | `int \| None` | The strength of a domain's backlink profile compared to the other websites in our database, with rank #1 being the st... |
| `backlinks` | `int \| None` | The total number of links from other websites pointing to a search result. |
| `domain_rating` | `float \| None` | The strength of a domain’s backlink profile compared to the others in our database on a 100-point scale. |
| `keywords` | `int \| None` | The total number of keywords that a search result ranks for in the top 100 organic positions. |
| `position` | `int` | The position of the search result in SERP. |
| `refdomains` | `int \| None` | (5 units) The total number of unique domains linking to a search result. |
| `title` | `str \| None` | The title of a ranking page. |
| `top_keyword` | `str \| None` | The keyword that brings the most organic traffic to a search result. |
| `top_keyword_volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for the top keyword over the latest known 12 month... |
| `traffic` | `int \| None` | (10 units) An estimation of the monthly organic search traffic that a result gets from all the keywords that it ranks... |
| `type` | `list[SerpFeaturesItemEnum1 \| None]` | The kind of the position: organic, paid, or a SERP feature. |
| `update_date` | `str` | The date when we checked search engine results for a keyword. |
| `url` | `str \| None` | The URL of a ranking page. |
| `url_rating` | `float \| None` | The strength of a page's backlink profile on a 100-point logarithmic scale. |
| `value` | `int \| None` | (10 units) The estimated value of a page’s monthly organic search traffic, in USD cents. |

---

## Site Audit

### `site_audit_issues()`

Project Issues.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `date_compared` | `str` | No | A timestamp in `YYYY-MM-DDThh:mm:ss` format specifying the crawl date to compare metrics with. Follows the same rules as the `date` field. |
| `date` | `str` | No | A timestamp in `YYYY-MM-DDThh:mm:ss` format specifying the crawl date to retrieve metrics from. Defaults to the most recent available crawl if omitted. For scheduled crawls, we return data from the latest crawl finished before the specified timestamp. For Always-on audit crawls, we return data as of the provided date and time. If the time component is omitted, it defaults to `00:00:00`. The timestamp is interpreted in UTC. |
| `project_id` | `int` | Yes | The unique identifier of the project. You can find it in the URL of your Site Audit project in Ahrefs: `https://app.ahrefs.com/site-audit/#project_id#` |

**Returns:** `list[SiteAuditIssuesData]`

| Field | Type | Description |
|-------|------|-------------|
| `issue_id` | `str` | The unique identifier of the issue. |
| `name` | `str` | The name of the issue. |
| `importance` | `str` | The importance of the issue. Possible values: `Error`, `Warning`, `Notice`. |
| `category` | `str` | The category of the issue. Possible values: `Internal pages`, `Indexability`, `Links`, `Redirects`, `Content`, `Socia... |
| `is_indexable` | `bool \| None` | True if the issue applies only to indexable pages. |
| `crawled` | `int` | Number of URLs currently affected by the issue. |
| `change` | `int \| None` | Difference in the number of affected URLs between the specified dates. |
| `added` | `int \| None` | Number of URLs that have the issue on the current date but did not have it on the previous date. |
| `new` | `int \| None` | Number of newly discovered URLs that have the issue on the current date. |
| `removed` | `int \| None` | Number of URLs that had the issue on the previous date but no longer have it on the current date. |
| `missing` | `int \| None` | Number of URLs that had the issue on the previous date but cannot be found on the current date. |

### `site_audit_page_content()`

Page content.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `date` | `str` | No | A timestamp in `YYYY-MM-DDThh:mm:ss` format specifying the crawl date to retrieve metrics from. Defaults to the most recent available crawl if omitted. For scheduled crawls, we return data from the latest crawl finished before the specified timestamp. For Always-on audit crawls, we return data as of the provided date and time. If the time component is omitted, it defaults to `00:00:00`. The timestamp is interpreted in UTC. |
| `target_url` | `str` | Yes | The URL of the page to retrieve content for. |
| `project_id` | `int` | Yes | The unique identifier of the project. Only projects with verified ownership are supported. You can find the project ID in the URL of your Site Audit project in Ahrefs: `https://app.ahrefs.com/site-audit/#project_id#` |

**Returns:** `SiteAuditPageContentData`

| Field | Type | Description |
|-------|------|-------------|
| `crawl_datetime` | `str` | The timestamp when the page was crawled. |
| `page_text` | `str \| None` | The text extracted from the page content. |
| `raw_html` | `str \| None` | The raw HTML of the page. |
| `rendered_html` | `str \| None` | The rendered HTML of the page. |

### `site_audit_page_explorer()`

Page explorer.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **ai_content_level**: The estimated percentage of AI-generated text on the page. Possible values: `None`, `Low`, `Moderate`, `High`, `Very High`   type: string nullable  **ai_content_status**: AI detection status for each page. Possible values: - `Success`: Content analyzed successfully - `Content_too_short`: Not enough text for reliable detection - `Not_eligible`: URL isn't an internal HTML page - `Failed`: Internal issue prevented detection - `Detection_off`: Disabled in Crawl settings   type: string nullable  **alternate**: The number of incoming external links from rel="alternate" attributes on the pages (data from Ahrefs' Site Explorer database)   type: integer nullable  **alternate_diff**: The number of incoming external links from rel="alternate" attributes on the pages (data from Ahrefs' Site Explorer database)   type: integer nullable  **alternate_prev**: The number of incoming external links from rel="alternate" attributes on the pages (data from Ahrefs' Site Explorer database)   type: integer nullable  **backlinks**: The number of incoming external links (both dofollow and nofollow) pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **backlinks_diff**: The number of incoming external links (both dofollow and nofollow) pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **backlinks_prev**: The number of incoming external links (both dofollow and nofollow) pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **canonical**: The URL of the canonical version of the page   type: url nullable  **canonical_code**: The HTTP status code of the canonical URL   type: integer nullable  **canonical_counts**: The number of incoming external links from canonical pages pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **canonical_counts_diff**: The number of incoming external links from canonical pages pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **canonical_counts_prev**: The number of incoming external links from canonical pages pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **canonical_group_hash**: The ID of the group of pages that have the same canonical URL   type: integer nullable  **canonical_is_canonical**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: boolean nullable  **canonical_is_canonical_prev**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: boolean nullable  **canonical_no_crawl_reason**: The reason why the canonical version of the page was not crawled   type: string nullable  **canonical_no_crawl_reason_prev**: The reason why the canonical version of the page was not crawled   type: string nullable  **canonical_prev**: The URL of the canonical version of the page   type: url nullable  **canonical_scheme**: The protocol of the canonical URL   type: string nullable  **canonical_scheme_prev**: The protocol of the canonical URL   type: string nullable  **compliant**: Indicates that the page is indexable. An indexable page is an HTML page returning the 200 HTTP status code that has neither the "rel=canonical" tag pointing to a different URL nor the "noindex" directive   type: boolean nullable  **compliant_prev**: Indicates that the page is indexable. An indexable page is an HTML page returning the 200 HTTP status code that has neither the "rel=canonical" tag pointing to a different URL nor the "noindex" directive   type: boolean nullable  **compression**: The data compression scheme   type: string nullable  **compression_prev**: The data compression scheme   type: string nullable  **content_encoding**: The Content-Encoding HTTP response header field   type: string nullable  **content_encoding_prev**: The Content-Encoding HTTP response header field   type: string nullable  **content_length**: The character length of content displayed on the page   type: integer nullable  **content_length_diff**: The character length of content displayed on the page   type: integer nullable  **content_length_prev**: The character length of content displayed on the page   type: integer nullable  **content_nr_word**: The word count of content displayed on the page   type: integer nullable  **content_nr_word_diff**: The word count of content displayed on the page   type: integer nullable  **content_nr_word_prev**: The word count of content displayed on the page   type: integer nullable  **content_type**: The Content-Type HTTP header of the page or resource. You can find the full list of content types [here](https://www.iana.org/assignments/media-types/media-types.xhtml)   type: string nullable  **content_type_prev**: The Content-Type HTTP header of the page or resource. You can find the full list of content types [here](https://www.iana.org/assignments/media-types/media-types.xhtml)   type: string nullable  **css_no_crawl_reason**: The reasons why CSS files linked from the page were not crawled   type: array(null)  **css_no_crawl_reason_prev**: The reasons why CSS files linked from the page were not crawled   type: array(null)  **curl_code**: CURLcode return code. You can find the full list of CURL codes [here](https://curl.haxx.se/libcurl/c/libcurl-errors.html)   type: integer  **depth**: The minimum number of clicks required for our crawler to reach the URL from the starting point of a crawl (seed page). Please note that redirects are also counted as a level   type: integer nullable  **depth_diff**: The minimum number of clicks required for our crawler to reach the URL from the starting point of a crawl (seed page). Please note that redirects are also counted as a level   type: integer nullable  **depth_prev**: The minimum number of clicks required for our crawler to reach the URL from the starting point of a crawl (seed page). Please note that redirects are also counted as a level   type: integer nullable  **dofollow**: The number of incoming external dofollow links pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **dofollow_prev**: The number of incoming external dofollow links pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **domain**: The domain name part of the URL   type: domain  **duplicate_content**: The number of pages with matching or appreciably similar content   type: integer nullable  **duplicate_content_canonical_hreflang**: The number of page groups with matching or appreciably similar content. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_content_canonical_hreflang_diff**: The number of page groups with matching or appreciably similar content. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_content_canonical_hreflang_prev**: The number of page groups with matching or appreciably similar content. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_content_diff**: The number of pages with matching or appreciably similar content   type: integer nullable  **duplicate_content_prev**: The number of pages with matching or appreciably similar content   type: integer nullable  **duplicate_description**: The number of pages that have the same meta description. If the page has more than one meta description, each will be checked for duplicates   type: integer nullable  **duplicate_description_canonical_hreflang**: The number of page groups that have the same meta description. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_description_canonical_hreflang_diff**: The number of page groups that have the same meta description. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_description_canonical_hreflang_prev**: The number of page groups that have the same meta description. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_description_diff**: The number of pages that have the same meta description. If the page has more than one meta description, each will be checked for duplicates   type: integer nullable  **duplicate_description_prev**: The number of pages that have the same meta description. If the page has more than one meta description, each will be checked for duplicates   type: integer nullable  **duplicate_group_identifier**: The ID of the group of pages that are interconnected via a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_h1**: The number of pages that have the same H1 subheader. If the page has more than one H1 subheader, each will be checked for duplicates   type: integer nullable  **duplicate_h1_diff**: The number of pages that have the same H1 subheader. If the page has more than one H1 subheader, each will be checked for duplicates   type: integer nullable  **duplicate_h1_prev**: The number of pages that have the same H1 subheader. If the page has more than one H1 subheader, each will be checked for duplicates   type: integer nullable  **duplicate_h1canonical_hreflang**: The number of page groups sharing the same H1 subheader. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_h1canonical_hreflang_diff**: The number of page groups sharing the same H1 subheader. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_h1canonical_hreflang_prev**: The number of page groups sharing the same H1 subheader. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_title**: The number of pages that have the same title. If the page has more than one title, each will be checked for duplicates   type: integer nullable  **duplicate_title_canonical_hreflang**: The number of page groups that have the same title. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_title_canonical_hreflang_diff**: The number of page groups that have the same title. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_title_canonical_hreflang_prev**: The number of page groups that have the same title. A group includes pages united by a common canonical URL, hreflang or pagination tags   type: integer nullable  **duplicate_title_diff**: The number of pages that have the same title. If the page has more than one title, each will be checked for duplicates   type: integer nullable  **duplicate_title_prev**: The number of pages that have the same title. If the page has more than one title, each will be checked for duplicates   type: integer nullable  **edu**: The number of incoming external links from .edu domains pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **edu_diff**: The number of incoming external links from .edu domains pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **edu_prev**: The number of incoming external links from .edu domains pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **external_code**: The list of HTTP status codes returned by the external URLs linked from the page   type: array(null)  **external_link_anchor**: The list of anchor texts used in external outgoing links on the page   type: array(null)  **external_link_anchor_prev**: The list of anchor texts used in external outgoing links on the page   type: array(null)  **external_link_domain**: The list of external domains linked to from the page   type: array(domain)  **external_link_domain_prev**: The list of external domains linked to from the page   type: array(domain)  **external_links**: The list of external outgoing links on the page   type: array(url)  **external_links_is_canonical**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: array(null)  **external_links_is_canonical_prev**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: array(null)  **external_links_prev**: The list of external outgoing links on the page   type: array(url)  **external_no_crawl_reason**: The reasons why the external URLs linked from the page were not crawled   type: array(null)  **external_no_crawl_reason_prev**: The reasons why the external URLs linked from the page were not crawled   type: array(null)  **external_scheme**: The protocols of the external outgoing links on the page   type: array(string)  **external_scheme_prev**: The protocols of the external outgoing links on the page   type: array(string)  **final_redirect**: The destination of the final redirecting URL   type: url nullable  **final_redirect_code**: The HTTP status code of the destination of the final redirecting URL   type: integer nullable  **final_redirect_no_crawl_reason**: The reason why the destination of the final redirecting URL was not crawled   type: string nullable  **final_redirect_no_crawl_reason_prev**: The reason why the destination of the final redirecting URL was not crawled   type: string nullable  **final_redirect_prev**: The destination of the final redirecting URL   type: url nullable  **found_in_sitemaps**: The list of sitemaps that reference the URL   type: array(url)  **found_in_sitemaps_length**: The number of sitemaps that reference the URL   type: integer  **found_in_sitemaps_prev**: The list of sitemaps that reference the URL   type: array(url)  **gov**: The total number of incoming external links from .gov domains pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **gov_diff**: The total number of incoming external links from .gov domains pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **gov_prev**: The total number of incoming external links from .gov domains pointing to the URL (data from Ahrefs' Site Explorer database). Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **h1**: The page H1 subheader   type: array(string)  **h1_prev**: The page H1 subheader   type: array(string)  **h1length**: The character length of the page H1 subheader   type: array(integer)  **h1length_prev**: The character length of the page H1 subheader   type: array(integer)  **h2**: The page H2 subheader   type: array(string)  **h2_prev**: The page H2 subheader   type: array(string)  **hash_content**: The page content fingerprint. Pages with matching or appreciably similar content have the same content hash   type: integer nullable  **hash_descriptions**: meta_descriptions.hash   type: array(integer)  **hash_h1**: The page H1 subheader fingerprint. Pages with matching H1 tags have the same H1 hash   type: array(integer)  **hash_text**: The page text fingerprint. Pages with matching content have the same text hash   type: integer nullable  **hash_titles**: The page title fingerprint. Pages with matching title tags have the same title hash   type: array(integer)  **hreflang**: Data from hreflang attributes   type: array(null)  **hreflang_code_is_valid**: Indicates that hreflang data is specified properly in the hreflang tags on the page. The language must be specified in [ISO 639-1 format](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), and optionally the region in [ISO 3166-1 Alpha 2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)   type: array(null)  **hreflang_code_is_valid_prev**: Indicates that hreflang data is specified properly in the hreflang tags on the page. The language must be specified in [ISO 639-1 format](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), and optionally the region in [ISO 3166-1 Alpha 2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)   type: array(null)  **hreflang_country**: The list of regions specified in the hreflang tags on the page   type: array(null)  **hreflang_country_prev**: The list of regions specified in the hreflang tags on the page   type: array(null)  **hreflang_group_hash**: The ID of the group of pages that have the same set of hreflang attributes with the same set of URLs in them   type: integer nullable  **hreflang_inlink_urls**: The list of incoming URLs with hreflang attribute   type: array(url)  **hreflang_inlink_urls_prev**: The list of incoming URLs with hreflang attribute   type: array(url)  **hreflang_issues**: The list of hreflang-related issues a page has   type: array(string)  **hreflang_issues_prev**: The list of hreflang-related issues a page has   type: array(string)  **hreflang_language**: The list of languages specified in the hreflang tags on the page   type: array(null)  **hreflang_language_prev**: The list of languages specified in the hreflang tags on the page   type: array(null)  **hreflang_link**: The list of URLs specified in the hreflang tags on the page   type: array(url)  **hreflang_link_is_canonical**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: array(null)  **hreflang_link_is_canonical_prev**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: array(null)  **hreflang_link_prev**: The list of URLs specified in the hreflang tags on the page   type: array(url)  **hreflang_no_crawl_reason**: The reasons why URLs specified in the hreflang tags on the page were not crawled   type: array(null)  **hreflang_no_crawl_reason_prev**: The reasons why URLs specified in the hreflang tags on the page were not crawled   type: array(null)  **hreflang_pages_urls**: List of hreflang-linked pages URLs the page belongs to   type: array(url)  **hreflang_pages_urls_count**: Count of hreflang-linked pages URLs the page belongs to   type: integer nullable  **hreflang_pages_urls_count_diff**: Count of hreflang-linked pages URLs the page belongs to   type: integer nullable  **hreflang_pages_urls_count_prev**: Count of hreflang-linked pages URLs the page belongs to   type: integer nullable  **hreflang_pages_urls_prev**: List of hreflang-linked pages URLs the page belongs to   type: array(url)  **hreflang_prev**: Data from hreflang attributes   type: array(null)  **html_lang**: Data from the page's HTML lang tag   type: string nullable  **html_lang_code_is_valid**: Indicates that the language (or language-region) code is specified properly in the HTML lang tag. The language must be specified in [ISO 639-1 format](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), and optionally the region in [ISO 3166-1 Alpha 2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)   type: boolean nullable  **html_lang_code_is_valid_prev**: Indicates that the language (or language-region) code is specified properly in the HTML lang tag. The language must be specified in [ISO 639-1 format](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), and optionally the region in [ISO 3166-1 Alpha 2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)   type: boolean nullable  **html_lang_country**: The region code specified in the page's HTML lang tag   type: string nullable  **html_lang_country_prev**: The region code specified in the page's HTML lang tag   type: string nullable  **html_lang_language**: The language code specified in the page's HTML lang tag   type: string nullable  **html_lang_language_prev**: The language code specified in the page's HTML lang tag   type: string nullable  **html_lang_prev**: Data from the page's HTML lang tag   type: string nullable  **http_code**: The HTTP status code returned by the URL   type: integer  **http_header**: The HTTP headers that the web server returns   type: array(string)  **http_header_prev**: The HTTP headers that the web server returns   type: array(string)  **http_header_robots**: Instructions for web crawlers specified in HTTP headers   type: array(string)  **http_header_robots_prev**: Instructions for web crawlers specified in HTTP headers   type: array(string)  **http_headers_size**: The size of the HTTP headers that the web server returns, measured in bytes   type: integer  **http_headers_size_diff**: The size of the HTTP headers that the web server returns, measured in bytes   type: integer nullable  **http_headers_size_prev**: The size of the HTTP headers that the web server returns, measured in bytes   type: integer nullable  **images_no_crawl_reason**: The reasons why images linked from the page were not crawled   type: array(null)  **images_no_crawl_reason_prev**: The reasons why images linked from the page were not crawled   type: array(null)  **incoming_all_links**: The number of incoming links to the URL of all types   type: integer nullable  **incoming_all_links_diff**: The number of incoming links to the URL of all types   type: integer nullable  **incoming_all_links_prev**: The number of incoming links to the URL of all types   type: integer nullable  **incoming_canonical**: Shows how many times the URL is linked to from a rel="canonical" element   type: integer nullable  **incoming_canonical_diff**: Shows how many times the URL is linked to from a rel="canonical" element   type: integer nullable  **incoming_canonical_prev**: Shows how many times the URL is linked to from a rel="canonical" element   type: integer nullable  **incoming_css**: The number of incoming links to the CSS file   type: integer nullable  **incoming_css_diff**: The number of incoming links to the CSS file   type: integer nullable  **incoming_css_prev**: The number of incoming links to the CSS file   type: integer nullable  **incoming_follow**: The number of incoming dofollow links to the URL from hyperlinks   type: integer nullable  **incoming_follow_diff**: The number of incoming dofollow links to the URL from hyperlinks   type: integer nullable  **incoming_follow_prev**: The number of incoming dofollow links to the URL from hyperlinks   type: integer nullable  **incoming_hreflang**: Shows how many times the URL is linked to from a rel="alternate" hreflang="x" attribute   type: integer nullable  **incoming_hreflang_diff**: Shows how many times the URL is linked to from a rel="alternate" hreflang="x" attribute   type: integer nullable  **incoming_hreflang_prev**: Shows how many times the URL is linked to from a rel="alternate" hreflang="x" attribute   type: integer nullable  **incoming_image**: The number of incoming links to the image file   type: integer nullable  **incoming_image_diff**: The number of incoming links to the image file   type: integer nullable  **incoming_image_prev**: The number of incoming links to the image file   type: integer nullable  **incoming_js**: The number of incoming links to the JS file   type: integer nullable  **incoming_js_diff**: The number of incoming links to the JS file   type: integer nullable  **incoming_js_prev**: The number of incoming links to the JS file   type: integer nullable  **incoming_links**: The number of incoming links to the URL from hyperlinks   type: integer nullable  **incoming_links_diff**: The number of incoming links to the URL from hyperlinks   type: integer nullable  **incoming_links_prev**: The number of incoming links to the URL from hyperlinks   type: integer nullable  **incoming_nofollow**: The number of incoming nofollow links to the URL from hyperlinks   type: integer nullable  **incoming_nofollow_diff**: The number of incoming nofollow links to the URL from hyperlinks   type: integer nullable  **incoming_nofollow_prev**: The number of incoming nofollow links to the URL from hyperlinks   type: integer nullable  **incoming_pagination**: Shows how many times the URL is linked to from rel="prev" or rel="next" elements on pages   type: integer nullable  **incoming_pagination_diff**: Shows how many times the URL is linked to from rel="prev" or rel="next" elements on pages   type: integer nullable  **incoming_pagination_prev**: Shows how many times the URL is linked to from rel="prev" or rel="next" elements on pages   type: integer nullable  **incoming_redirect**: The number of incoming redirecting links to the URL   type: integer nullable  **incoming_redirect_diff**: The number of incoming redirecting links to the URL   type: integer nullable  **incoming_redirect_prev**: The number of incoming redirecting links to the URL   type: integer nullable  **indexnow_error**: The error description for a failed auto-submission   type: string nullable  **indexnow_error_prev**: The error description for a failed auto-submission   type: string nullable  **indexnow_reason**: The reason the page was considered for auto-submission to IndexNow   type: string nullable  **indexnow_reason_prev**: The reason the page was considered for auto-submission to IndexNow   type: string nullable  **indexnow_status**: The status of IndexNow auto-submission. Possible values:  - **Success:** The page was successfully submitted to IndexNow. - **No changes detected:** No changes were detected on the page; submission was not required. - **Not eligible:** The URL isn't eligible for submission, e.g., it's not an indexable HTML page. - **Invalid API key:** IndexNow submission failed due to an invalid API key. - **Failed:** Submission to IndexNow failed; see details for the reason. - **Auto-submission is off:** Automatic submission is disabled in Crawl settings   type: string nullable  **indexnow_status_prev**: The status of IndexNow auto-submission. Possible values:  - **Success:** The page was successfully submitted to IndexNow. - **No changes detected:** No changes were detected on the page; submission was not required. - **Not eligible:** The URL isn't eligible for submission, e.g., it's not an indexable HTML page. - **Invalid API key:** IndexNow submission failed due to an invalid API key. - **Failed:** Submission to IndexNow failed; see details for the reason. - **Auto-submission is off:** Automatic submission is disabled in Crawl settings   type: string nullable  **indexnow_submitted_at**: The date and time when the URL was auto-submitted to IndexNow   type: date nullable  **indexnow_submitted_at_prev**: The date and time when the URL was auto-submitted to IndexNow   type: date nullable  **internal_code**: The list of HTTP status codes returned by the internal URLs linked to from the page   type: array(null)  **internal_inlink_urls**: The list of URLs for incoming internal links   type: array(url)  **internal_inlink_urls_prev**: The list of URLs for incoming internal links   type: array(url)  **internal_link_anchor**: The list of anchor texts used in internal outgoing links on the page   type: array(null)  **internal_link_anchor_prev**: The list of anchor texts used in internal outgoing links on the page   type: array(null)  **internal_link_domain**: The domain (or its subdomains, depending on the scope of the crawl) linked to from internal outgoing links on the page   type: array(domain)  **internal_link_domain_prev**: The domain (or its subdomains, depending on the scope of the crawl) linked to from internal outgoing links on the page   type: array(domain)  **internal_links**: The list of internal outgoing links on the page   type: array(url)  **internal_links_is_canonical**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: array(null)  **internal_links_is_canonical_prev**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: array(null)  **internal_links_prev**: The list of internal outgoing links on the page   type: array(url)  **internal_no_crawl_reason**: The reasons why the internal URLs linked to from the page were not crawled   type: array(null)  **internal_no_crawl_reason_prev**: The reasons why the internal URLs linked to from the page were not crawled   type: array(null)  **internal_scheme**: The protocols of the internal outgoing links on the page   type: array(string)  **internal_scheme_prev**: The protocols of the internal outgoing links on the page   type: array(string)  **is_html**: Indicates that the content type of the web document is HTML   type: boolean  **is_in_sitemap**: Indicates that the URL is included in the website's sitemap file   type: boolean nullable  **is_in_sitemap_prev**: Indicates that the URL is included in the website's sitemap file   type: boolean nullable  **is_page_title_used_in_serp**: Indicates that the page and SERP titles match   type: boolean nullable  **is_redirect_loop**: Checks if the URL has a redirect loop   type: boolean nullable  **is_redirect_loop_prev**: Checks if the URL has a redirect loop   type: boolean nullable  **is_rendered**: Indicates that the crawler had executed JavaScript on the page to generate content   type: boolean nullable  **is_rendered_prev**: Indicates that the crawler had executed JavaScript on the page to generate content   type: boolean nullable  **is_valid_internal_html**: The HTML page on the crawled domain or its subdomain that returns a 200 HTTP status code   type: boolean  **is_valid_internal_html_prev**: The HTML page on the crawled domain or its subdomain that returns a 200 HTTP status code   type: boolean nullable  **js_no_crawl_reason**: The reasons why JavaScript files linked from the page were not crawled   type: array(null)  **js_no_crawl_reason_prev**: The reasons why JavaScript files linked from the page were not crawled   type: array(null)  **jsonld_attributes**: Names of the schema properties found on the page (with indices)   type: array(string)  **jsonld_attributes_prev**: Names of the schema properties found on the page (with indices)   type: array(string)  **jsonld_schema_types**: Schema objects found on the page   type: array(string)  **jsonld_schema_types_prev**: Schema objects found on the page   type: array(string)  **jsonld_validation_kinds**: Issues with the structured data found on the page   type: array(string)  **jsonld_validation_kinds_prev**: Issues with the structured data found on the page   type: array(string)  **jsonld_values**: Values of the schema properties found on the page   type: array(string)  **jsonld_values_prev**: Values of the schema properties found on the page   type: array(string)  **keywords**: The page meta keywords   type: array(string)  **keywords_prev**: The page meta keywords   type: array(string)  **length**: The character length of the URL   type: integer  **links_count_css**: The number of CSS files linked from the page   type: integer nullable  **links_count_css_prev**: The number of CSS files linked from the page   type: integer nullable  **links_count_external**: The number of external outgoing links on the page   type: integer nullable  **links_count_external3xx**: The number of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: integer nullable  **links_count_external3xx_diff**: The number of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: integer nullable  **links_count_external3xx_prev**: The number of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: integer nullable  **links_count_external4xx**: The number of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: integer nullable  **links_count_external4xx_diff**: The number of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: integer nullable  **links_count_external4xx_prev**: The number of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: integer nullable  **links_count_external5xx**: The number of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: integer nullable  **links_count_external5xx_diff**: The number of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: integer nullable  **links_count_external5xx_prev**: The number of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: integer nullable  **links_count_external_diff**: The number of external outgoing links on the page   type: integer nullable  **links_count_external_follow**: The number of external outgoing dofollow links on the page   type: integer nullable  **links_count_external_follow_diff**: The number of external outgoing dofollow links on the page   type: integer nullable  **links_count_external_follow_prev**: The number of external outgoing dofollow links on the page   type: integer nullable  **links_count_external_nofollow**: The number of external outgoing nofollow links on the page   type: integer nullable  **links_count_external_nofollow_diff**: The number of external outgoing nofollow links on the page   type: integer nullable  **links_count_external_nofollow_prev**: The number of external outgoing nofollow links on the page   type: integer nullable  **links_count_external_non_canonical**: The number of external outgoing links on the page that point to non-canonical pages   type: integer nullable  **links_count_external_non_canonical_diff**: The number of external outgoing links on the page that point to non-canonical pages   type: integer nullable  **links_count_external_non_canonical_prev**: The number of external outgoing links on the page that point to non-canonical pages   type: integer nullable  **links_count_external_prev**: The number of external outgoing links on the page   type: integer nullable  **links_count_external_xxx**: The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: integer nullable  **links_count_external_xxx_diff**: The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: integer nullable  **links_count_external_xxx_prev**: The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: integer nullable  **links_count_images**: The number of images linked from the page   type: integer nullable  **links_count_images_diff**: The number of images linked from the page   type: integer nullable  **links_count_images_prev**: The number of images linked from the page   type: integer nullable  **links_count_images_with_alt**: The number of images linked from the page that have an alt attribute (alternate text)   type: integer nullable  **links_count_images_with_alt_diff**: The number of images linked from the page that have an alt attribute (alternate text)   type: integer nullable  **links_count_images_with_alt_prev**: The number of images linked from the page that have an alt attribute (alternate text)   type: integer nullable  **links_count_images_without_alt**: The number of images linked from the page that have no alt attribute (alternate text)   type: integer nullable  **links_count_images_without_alt_diff**: The number of images linked from the page that have no alt attribute (alternate text)   type: integer nullable  **links_count_images_without_alt_prev**: The number of images linked from the page that have no alt attribute (alternate text)   type: integer nullable  **links_count_internal**: The number of internal outgoing links on the page   type: integer nullable  **links_count_internal3xx**: The number of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: integer nullable  **links_count_internal3xx_diff**: The number of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: integer nullable  **links_count_internal3xx_prev**: The number of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: integer nullable  **links_count_internal4xx**: The number of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: integer nullable  **links_count_internal4xx_diff**: The number of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: integer nullable  **links_count_internal4xx_prev**: The number of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: integer nullable  **links_count_internal5xx**: The number of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: integer nullable  **links_count_internal5xx_diff**: The number of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: integer nullable  **links_count_internal5xx_prev**: The number of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: integer nullable  **links_count_internal_diff**: The number of internal outgoing links on the page   type: integer nullable  **links_count_internal_follow**: The number of internal outgoing dofollow links on the page   type: integer nullable  **links_count_internal_follow_diff**: The number of internal outgoing dofollow links on the page   type: integer nullable  **links_count_internal_follow_prev**: The number of internal outgoing dofollow links on the page   type: integer nullable  **links_count_internal_nofollow**: The number of internal outgoing nofollow links on the page   type: integer nullable  **links_count_internal_nofollow_diff**: The number of internal outgoing nofollow links on the page   type: integer nullable  **links_count_internal_nofollow_prev**: The number of internal outgoing nofollow links on the page   type: integer nullable  **links_count_internal_non_canonical**: The number of internal outgoing links on the page that point to non-canonical pages   type: integer nullable  **links_count_internal_non_canonical_diff**: The number of internal outgoing links on the page that point to non-canonical pages   type: integer nullable  **links_count_internal_non_canonical_prev**: The number of internal outgoing links on the page that point to non-canonical pages   type: integer nullable  **links_count_internal_prev**: The number of internal outgoing links on the page   type: integer nullable  **links_count_internal_xxx**: The number of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: integer nullable  **links_count_internal_xxx_diff**: The number of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: integer nullable  **links_count_internal_xxx_prev**: The number of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: integer nullable  **links_count_js**: The number of JavaScript files linked from the page   type: integer nullable  **links_count_js_diff**: The number of JavaScript files linked from the page   type: integer nullable  **links_count_js_prev**: The number of JavaScript files linked from the page   type: integer nullable  **links_css**: The list of CSS files linked from the page   type: array(url)  **links_css_code**: The list of HTTP status codes returned by CSS files linked from the page   type: array(null)  **links_css_domain**: The list of domains that contain CSS files linked from the page   type: array(domain)  **links_css_domain_prev**: The list of domains that contain CSS files linked from the page   type: array(domain)  **links_css_prev**: The list of CSS files linked from the page   type: array(url)  **links_css_scheme**: The protocols of CSS files linked from the page   type: array(string)  **links_css_scheme_prev**: The protocols of CSS files linked from the page   type: array(string)  **links_external3xx**: The list of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: array(url)  **links_external3xx_prev**: The list of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: array(url)  **links_external4xx**: The list of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: array(url)  **links_external4xx_prev**: The list of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: array(url)  **links_external5xx**: The list of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: array(url)  **links_external5xx_prev**: The list of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: array(url)  **links_external_follow**: The list of external outgoing dofollow links on the page   type: array(url)  **links_external_follow_prev**: The list of external outgoing dofollow links on the page   type: array(url)  **links_external_nofollow**: The list of external outgoing nofollow links on the page   type: array(url)  **links_external_nofollow_prev**: The list of external outgoing nofollow links on the page   type: array(url)  **links_external_non_canonical**: The list of external outgoing links on the page that point to non-canonical pages   type: array(url)  **links_external_non_canonical_prev**: The list of external outgoing links on the page that point to non-canonical pages   type: array(url)  **links_external_xxx**: The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: array(url)  **links_external_xxx_prev**: The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: array(url)  **links_hreflang_code**: The list of HTTP status codes returned by the URLs specified in hreflang tags on the page   type: array(null)  **links_images**: The list of images linked from the page   type: array(url)  **links_images_alt**: The list of alternate texts of images linked from the page   type: array(null)  **links_images_alt_prev**: The list of alternate texts of images linked from the page   type: array(null)  **links_images_code**: The list of HTTP status codes returned by images linked from the page   type: array(null)  **links_images_domain**: The list of domains that contain images linked from the page   type: array(domain)  **links_images_domain_prev**: The list of domains that contain images linked from the page   type: array(domain)  **links_images_prev**: The list of images linked from the page   type: array(url)  **links_images_scheme**: The protocols of images linked from the page   type: array(string)  **links_images_scheme_prev**: The protocols of images linked from the page   type: array(string)  **links_images_with_alt**: The list of images linked from the page that have an alt attribute (alternate text)   type: array(url)  **links_images_with_alt_prev**: The list of images linked from the page that have an alt attribute (alternate text)   type: array(url)  **links_images_without_alt**: The list of images linked from the page that have no alt attribute (alternate text)   type: array(url)  **links_images_without_alt_prev**: The list of images linked from the page that have no alt attribute (alternate text)   type: array(url)  **links_internal3xx**: The list of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: array(url)  **links_internal3xx_prev**: The list of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status codes   type: array(url)  **links_internal4xx**: The list of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: array(url)  **links_internal4xx_prev**: The list of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP status codes   type: array(url)  **links_internal5xx**: The list of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: array(url)  **links_internal5xx_prev**: The list of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP status codes   type: array(url)  **links_internal_follow**: The list of internal outgoing dofollow links on the page   type: array(url)  **links_internal_follow_prev**: The list of internal outgoing dofollow links on the page   type: array(url)  **links_internal_nofollow**: The list of internal outgoing nofollow links on the page   type: array(url)  **links_internal_nofollow_prev**: The list of internal outgoing nofollow links on the page   type: array(url)  **links_internal_non_canonical**: The list of internal outgoing links on the page that point to non-canonical pages   type: array(url)  **links_internal_non_canonical_prev**: The list of internal outgoing links on the page that point to non-canonical pages   type: array(url)  **links_internal_xxx**: The list of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: array(url)  **links_internal_xxx_prev**: The list of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4xx, 5xx or return no status code   type: array(url)  **links_js**: The list of JavaScript files linked from the page   type: array(url)  **links_js_code**: The list of HTTP status codes returned by JavaScript files linked from the page   type: array(null)  **links_js_domain**: The list of domains that contain JavaScript files linked from the page   type: array(domain)  **links_js_domain_prev**: The list of domains that contain JavaScript files linked from the page   type: array(domain)  **links_js_prev**: The list of JavaScript files linked from the page   type: array(url)  **links_js_scheme**: The protocols of JavaScript files linked from the page   type: array(string)  **links_js_scheme_prev**: The protocols of JavaScript files linked from the page   type: array(string)  **loading_time**: The time it takes for the crawler to load the full content of the document, measured in milliseconds   type: integer  **loading_time_diff**: The time it takes for the crawler to load the full content of the document, measured in milliseconds   type: integer nullable  **loading_time_prev**: The time it takes for the crawler to load the full content of the document, measured in milliseconds   type: integer nullable  **meta_description**: Meta description   type: array(string)  **meta_description_length**: Meta description length   type: array(integer)  **meta_description_length_prev**: Meta description length   type: array(integer)  **meta_description_prev**: Meta description   type: array(string)  **meta_refresh**: The time set in a meta refresh tag, in seconds   type: array(string)  **meta_refresh_prev**: The time set in a meta refresh tag, in seconds   type: array(string)  **meta_robots**: Instructions for web crawlers specified in HTML robots meta tags on the page   type: array(string)  **meta_robots_prev**: Instructions for web crawlers specified in HTML robots meta tags on the page   type: array(string)  **meta_twitter_tags_app_google_play**: The app ID in the Google Play Store specified in the twitter:app:id:ipad meta property   type: string nullable  **meta_twitter_tags_app_google_play_prev**: The app ID in the Google Play Store specified in the twitter:app:id:ipad meta property   type: string nullable  **meta_twitter_tags_app_ipad**: The app ID in the iTunes App Store specified in the twitter:app:id:ipad meta property   type: string nullable  **meta_twitter_tags_app_ipad_prev**: The app ID in the iTunes App Store specified in the twitter:app:id:ipad meta property   type: string nullable  **meta_twitter_tags_app_iphone**: The app ID in the iTunes App Store specified in the twitter:app:id:iphone meta property   type: string nullable  **meta_twitter_tags_app_iphone_prev**: The app ID in the iTunes App Store specified in the twitter:app:id:iphone meta property   type: string nullable  **meta_twitter_tags_attributes**: The list of X (Twitter) Card properties on the page   type: array(string)  **meta_twitter_tags_attributes_prev**: The list of X (Twitter) Card properties on the page   type: array(string)  **meta_twitter_tags_card**: The X (Twitter) Card type can be "summary", "summary\_large\_image", "app", or "player"   type: string nullable  **meta_twitter_tags_card_prev**: The X (Twitter) Card type can be "summary", "summary\_large\_image", "app", or "player"   type: string nullable  **meta_twitter_tags_description**: meta_twitter_tags.description   type: string nullable  **meta_twitter_tags_description_prev**: meta_twitter_tags.description   type: string nullable  **meta_twitter_tags_image**: The image URL specified in the twitter:image meta property   type: string nullable  **meta_twitter_tags_image_prev**: The image URL specified in the twitter:image meta property   type: string nullable  **meta_twitter_tags_image_url_invalid**: Indicates that the URL specified in the twitter:image meta property is a valid absolute URL   type: boolean nullable  **meta_twitter_tags_image_url_invalid_prev**: Indicates that the URL specified in the twitter:image meta property is a valid absolute URL   type: boolean nullable  **meta_twitter_tags_player**: The HTTPS URL of player iframe specified in the twitter:player meta property   type: string nullable  **meta_twitter_tags_player_height**: The height of iframe in pixels specified in the twitter:player:width meta property   type: integer nullable  **meta_twitter_tags_player_height_diff**: The height of iframe in pixels specified in the twitter:player:width meta property   type: integer nullable  **meta_twitter_tags_player_height_prev**: The height of iframe in pixels specified in the twitter:player:width meta property   type: integer nullable  **meta_twitter_tags_player_prev**: The HTTPS URL of player iframe specified in the twitter:player meta property   type: string nullable  **meta_twitter_tags_player_width**: The width of iframe in pixels specified in the twitter:player:width meta property   type: integer nullable  **meta_twitter_tags_player_width_diff**: The width of iframe in pixels specified in the twitter:player:width meta property   type: integer nullable  **meta_twitter_tags_player_width_prev**: The width of iframe in pixels specified in the twitter:player:width meta property   type: integer nullable  **meta_twitter_tags_site**: The X (Twitter) handle specified in the twitter:site meta property   type: string nullable  **meta_twitter_tags_site_prev**: The X (Twitter) handle specified in the twitter:site meta property   type: string nullable  **meta_twitter_tags_title**: The title text specified in the twitter:title meta property   type: string nullable  **meta_twitter_tags_title_prev**: The title text specified in the twitter:title meta property   type: string nullable  **meta_twitter_tags_valid**: Indicates that the page has all the necessary tags required in a X (Twitter) Card   type: boolean nullable  **meta_twitter_tags_valid_prev**: Indicates that the page has all the necessary tags required in a X (Twitter) Card   type: boolean nullable  **meta_twitter_tags_values**: Data from the X (Twitter) Card properties on the page   type: array(string)  **meta_twitter_tags_values_prev**: Data from the X (Twitter) Card properties on the page   type: array(string)  **navigation_next**: The URL specified in the rel="next" element on the page   type: url nullable  **navigation_next_code**: The HTTP status code returned by the URL specified in the rel="next" element on a page   type: integer nullable  **navigation_next_no_crawl_reason**: The reason why the URL specified in the rel="next" element on a page was not crawled   type: string nullable  **navigation_next_no_crawl_reason_prev**: The reason why the URL specified in the rel="next" element on a page was not crawled   type: string nullable  **navigation_next_prev**: The URL specified in the rel="next" element on the page   type: url nullable  **navigation_prev_code**: The HTTP status code returned by the URL specified in the rel="prev" element on a page   type: integer nullable  **navigation_prev_no_crawl_reason**: The reason why the URL specified in the rel="prev" element on a page was not crawled   type: string nullable  **navigation_prev_no_crawl_reason_prev**: The reason why the URL specified in the rel="prev" element on a page was not crawled   type: string nullable  **no_crawl_reason**: The reason why the URL was not crawled   type: string nullable  **no_crawl_reason_prev**: The reason why the URL was not crawled   type: string nullable  **nofollow**: The number of incoming external nofollow links pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **nofollow_diff**: The number of incoming external nofollow links pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **nofollow_prev**: The number of incoming external nofollow links pointing to the URL. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **nr_h1**: The number of H1 subheaders on the page   type: integer  **nr_h1_prev**: The number of H1 subheaders on the page   type: integer nullable  **nr_meta_description**: Number of Meta descriptions   type: integer  **nr_meta_description_diff**: Number of Meta descriptions   type: integer nullable  **nr_meta_description_prev**: Number of Meta descriptions   type: integer nullable  **nr_redirect_chain_urls**: The number of redirect chain URLs   type: integer nullable  **nr_redirect_chain_urls_diff**: The number of redirect chain URLs   type: integer nullable  **nr_redirect_chain_urls_prev**: The number of redirect chain URLs   type: integer nullable  **nr_titles**: The number of title tags on the page   type: integer  **nr_titles_diff**: The number of title tags on the page   type: integer nullable  **nr_titles_prev**: The number of title tags on the page   type: integer nullable  **og_tags_attributes**: The list of Open Graph properties on a page   type: array(string)  **og_tags_attributes_prev**: The list of Open Graph properties on a page   type: array(string)  **og_tags_image**: The image URL specified in the og:image meta property   type: string nullable  **og_tags_image_prev**: The image URL specified in the og:image meta property   type: string nullable  **og_tags_image_url_invalid**: Indicates that the URL specified in the og:image meta property is a valid absolute URL   type: boolean nullable  **og_tags_image_url_invalid_prev**: Indicates that the URL specified in the og:image meta property is a valid absolute URL   type: boolean nullable  **og_tags_inconsistent_canonical**: Indicates that the URL specified in the og:url meta property matches the URL specified as the canonical version of the page   type: boolean nullable  **og_tags_inconsistent_canonical_prev**: Indicates that the URL specified in the og:url meta property matches the URL specified as the canonical version of the page   type: boolean nullable  **og_tags_title**: The title text specified in the og:title meta property   type: string nullable  **og_tags_title_prev**: The title text specified in the og:title meta property   type: string nullable  **og_tags_type**: The object type specified in the og:type meta property   type: string nullable  **og_tags_type_prev**: The object type specified in the og:type meta property   type: string nullable  **og_tags_url**: The URL specified in the og:url meta property   type: string nullable  **og_tags_url_prev**: The URL specified in the og:url meta property   type: string nullable  **og_tags_url_valid**: Indicates that the URL specified in the og:url meta property is a valid absolute URL   type: boolean nullable  **og_tags_url_valid_prev**: Indicates that the URL specified in the og:url meta property is a valid absolute URL   type: boolean nullable  **og_tags_valid**: Indicates that the page has all four required Open Graph properties: og:title, og:type, og:image, and og:url   type: boolean nullable  **og_tags_valid_prev**: Indicates that the page has all four required Open Graph properties: og:title, og:type, og:image, and og:url   type: boolean nullable  **og_tags_value**: Data from Open Graph properties on a page   type: array(string)  **og_tags_value_prev**: Data from Open Graph properties on a page   type: array(string)  **origin**: Shows where the URL was originally found during the crawl   type: url nullable  **origin_prev**: Shows where the URL was originally found during the crawl   type: url nullable  **page_is_nofollow**: Check if the page is nofollow, based on http header and meta robots instructions   type: boolean nullable  **page_is_nofollow_prev**: Check if the page is nofollow, based on http header and meta robots instructions   type: boolean nullable  **page_is_noindex**: Check if the page is noindex, based on http header and meta robots instructions   type: boolean nullable  **page_is_noindex_prev**: Check if the page is noindex, based on http header and meta robots instructions   type: boolean nullable  **page_rating**: Page Rating (PR) shows the URL's internal and external backlink profile strength relative to other URLs included in the crawl   type: integer nullable  **page_raw_ur**: URL Rating (UR) shows the strength of your target page's backlink profile on a 100-point logarithmic scale. [Learn more](https://help.ahrefs.com/en/articles/72658-what-is-url-rating-ur)   type: integer nullable  **page_raw_ur_diff**: URL Rating (UR) shows the strength of your target page's backlink profile on a 100-point logarithmic scale. [Learn more](https://help.ahrefs.com/en/articles/72658-what-is-url-rating-ur)   type: integer nullable  **page_raw_ur_prev**: URL Rating (UR) shows the strength of your target page's backlink profile on a 100-point logarithmic scale. [Learn more](https://help.ahrefs.com/en/articles/72658-what-is-url-rating-ur)   type: integer nullable  **page_type**: Site Audit categorizes URLs as HTML Pages, Resource files (image, CSS or JavaScript), XML Sitemaps     and Robots.txt. If a page doesn't return status code 200 or has a content type that isn't covered by the categories above, it's     considered as "Other". Since we can't determine what these pages are, we further classify them based on how incoming links reference     them: as resources (receive resource incoming links) or as pages (receive non-resource incoming links)   type: array(string)  **page_type_prev**: Site Audit categorizes URLs as HTML Pages, Resource files (image, CSS or JavaScript), XML Sitemaps     and Robots.txt. If a page doesn't return status code 200 or has a content type that isn't covered by the categories above, it's     considered as "Other". Since we can't determine what these pages are, we further classify them based on how incoming links reference     them: as resources (receive resource incoming links) or as pages (receive non-resource incoming links)   type: array(string)  **pagination_group**: The ID of the group of pages interconnected via their rel="next" and rel="prev" links   type: integer nullable  **pagination_group_prev**: The ID of the group of pages interconnected via their rel="next" and rel="prev" links   type: integer nullable  **positions**: The number of keywords the page is ranking for in top 100 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_diff**: The number of keywords the page is ranking for in top 100 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_prev**: The number of keywords the page is ranking for in top 100 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_top10**: The number of keywords the page is ranking for in top 10 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_top10_diff**: The number of keywords the page is ranking for in top 10 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_top10_prev**: The number of keywords the page is ranking for in top 10 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_top3**: The number of keywords the page is ranking for in top 3 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_top3_diff**: The number of keywords the page is ranking for in top 3 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **positions_top3_prev**: The number of keywords the page is ranking for in top 3 organic search results worldwide (data from Ahrefs' Site Explorer)   type: integer nullable  **psi_crux_cls_category**: Your CLS category will be either Good (<0.1), Needs Improvement (0.1 - 0.25), or Poor (>0.25). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: string nullable  **psi_crux_cls_category_prev**: Your CLS category will be either Good (<0.1), Needs Improvement (0.1 - 0.25), or Poor (>0.25). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: string nullable  **psi_crux_cls_distributions_proportion**: What % of collected CLS metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: array(null)  **psi_crux_cls_distributions_proportion_prev**: What % of collected CLS metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: array(null)  **psi_crux_cls_percentile**: Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_crux_cls_percentile_diff**: Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: integer nullable  **psi_crux_cls_percentile_prev**: Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_crux_fid_category**: Your FID category will be either Good (<100 ms), Needs Improvement (100 ms - 300 ms), or Poor (>300 ms). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: string nullable  **psi_crux_fid_category_prev**: Your FID category will be either Good (<100 ms), Needs Improvement (100 ms - 300 ms), or Poor (>300 ms). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: string nullable  **psi_crux_fid_distributions_proportion**: What % of collected FID metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: array(null)  **psi_crux_fid_distributions_proportion_prev**: What % of collected FID metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: array(null)  **psi_crux_fid_percentile**: First Input Delay measures interactivity. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_crux_fid_percentile_diff**: First Input Delay measures interactivity. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: integer nullable  **psi_crux_fid_percentile_prev**: First Input Delay measures interactivity. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_crux_inp_category**: Your INP category will be either Good (<200 ms), Needs Improvement (200 ms - 500 ms), or Poor (>500 ms). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://web.dev/inp/)   type: string nullable  **psi_crux_inp_category_prev**: Your INP category will be either Good (<200 ms), Needs Improvement (200 ms - 500 ms), or Poor (>500 ms). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://web.dev/inp/)   type: string nullable  **psi_crux_inp_distributions_proportion**: What % of collected INP metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://web.dev/inp/)   type: array(null)  **psi_crux_inp_distributions_proportion_prev**: What % of collected INP metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://web.dev/inp/)   type: array(null)  **psi_crux_inp_percentile**: Interaction to Next Paint measure overall responsiveness of a page to user interactions. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://web.dev/inp/)   type: float nullable  **psi_crux_inp_percentile_diff**: Interaction to Next Paint measure overall responsiveness of a page to user interactions. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://web.dev/inp/)   type: integer nullable  **psi_crux_inp_percentile_prev**: Interaction to Next Paint measure overall responsiveness of a page to user interactions. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://web.dev/inp/)   type: float nullable  **psi_crux_lcp_category**: Your LCP category will be either Good (<2.5 sec), Needs Improvement (2.5 sec - 4.0 sec), or Poor (>4.0 sec). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: string nullable  **psi_crux_lcp_category_prev**: Your LCP category will be either Good (<2.5 sec), Needs Improvement (2.5 sec - 4.0 sec), or Poor (>4.0 sec). The category is based on the lowest threshold that includes 75% of page views. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: string nullable  **psi_crux_lcp_distributions_proportion**: What % of collected LCP metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: array(null)  **psi_crux_lcp_distributions_proportion_prev**: What % of collected LCP metrics are in each associated threshold, which categorize performance as either "Good", "Needs Improvement", or "Poor". [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: array(null)  **psi_crux_lcp_percentile**: Largest Contentful Paint measures visual loading performance. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_crux_lcp_percentile_diff**: Largest Contentful Paint measures visual loading performance. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: integer nullable  **psi_crux_lcp_percentile_prev**: Largest Contentful Paint measures visual loading performance. This score comes from the Chrome User Experience Report which looks at real user data. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_lighthouse_cls_error_message**: The message returned by Lighthouse if there is an error when measuring CLS   type: string nullable  **psi_lighthouse_cls_error_message_prev**: The message returned by Lighthouse if there is an error when measuring CLS   type: string nullable  **psi_lighthouse_cls_value**: Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting. This score comes from Lighthouse in a simulated test environment. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_lighthouse_cls_value_diff**: Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting. This score comes from Lighthouse in a simulated test environment. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: integer nullable  **psi_lighthouse_cls_value_prev**: Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting. This score comes from Lighthouse in a simulated test environment. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_lighthouse_lcp_error_message**: The message returned by Lighthouse if there is an error when measuring LCP   type: string nullable  **psi_lighthouse_lcp_error_message_prev**: The message returned by Lighthouse if there is an error when measuring LCP   type: string nullable  **psi_lighthouse_lcp_value**: Largest Contentful Paint measures visual loading performance. This score comes from Lighthouse in a simulated test environment. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_lighthouse_lcp_value_diff**: Largest Contentful Paint measures visual loading performance. This score comes from Lighthouse in a simulated test environment. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: integer nullable  **psi_lighthouse_lcp_value_prev**: Largest Contentful Paint measures visual loading performance. This score comes from Lighthouse in a simulated test environment. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_lighthouse_score**: This score uses multiple Lighthouse speed metrics to create a summary of the page's performance and use of best practices. Scores will be considered Good (>90), Needs Improvement (50-90), or Poor (<50). [Learn more](https://web.dev/performance-scoring/)   type: integer nullable  **psi_lighthouse_score_diff**: This score uses multiple Lighthouse speed metrics to create a summary of the page's performance and use of best practices. Scores will be considered Good (>90), Needs Improvement (50-90), or Poor (<50). [Learn more](https://web.dev/performance-scoring/)   type: integer nullable  **psi_lighthouse_score_prev**: This score uses multiple Lighthouse speed metrics to create a summary of the page's performance and use of best practices. Scores will be considered Good (>90), Needs Improvement (50-90), or Poor (<50). [Learn more](https://web.dev/performance-scoring/)   type: integer nullable  **psi_lighthouse_tbt_error_message**: The message returned by Lighthouse if there is an error when measuring TBT   type: string nullable  **psi_lighthouse_tbt_error_message_prev**: The message returned by Lighthouse if there is an error when measuring TBT   type: string nullable  **psi_lighthouse_tbt_value**: Total Blocking Time measures the total amount of time that a page is blocked from responding to user interactions. This score comes from Lighthouse in a simulated test environment. TBT is the recommended alternative to FID for lab tests. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_lighthouse_tbt_value_diff**: Total Blocking Time measures the total amount of time that a page is blocked from responding to user interactions. This score comes from Lighthouse in a simulated test environment. TBT is the recommended alternative to FID for lab tests. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: integer nullable  **psi_lighthouse_tbt_value_prev**: Total Blocking Time measures the total amount of time that a page is blocked from responding to user interactions. This score comes from Lighthouse in a simulated test environment. TBT is the recommended alternative to FID for lab tests. [Learn more](https://ahrefs.com/blog/core-web-vitals/)   type: float nullable  **psi_mobile_issues**: List of mobile-related issues on the page detected by Lighthouse   type: array(string)  **psi_mobile_issues_explanations**: Details about the mobile issues detected by Lighthouse   type: array(string)  **psi_mobile_issues_explanations_prev**: Details about the mobile issues detected by Lighthouse   type: array(string)  **psi_mobile_issues_prev**: List of mobile-related issues on the page detected by Lighthouse   type: array(string)  **psi_request_error_message**: The message returned by PageSpeed Insights API if there is an error. [Learn more](https://help.ahrefs.com/en/articles/5369589-how-to-see-core-web-vitals-and-other-speed-metrics-in-site-audit-tool)   type: string nullable  **psi_request_error_message_prev**: The message returned by PageSpeed Insights API if there is an error. [Learn more](https://help.ahrefs.com/en/articles/5369589-how-to-see-core-web-vitals-and-other-speed-metrics-in-site-audit-tool)   type: string nullable  **psi_request_status**: The result of a request to PageSpeed Insights API. [Learn more](https://help.ahrefs.com/en/articles/5369589-how-to-see-core-web-vitals-and-other-speed-metrics-in-site-audit-tool)   type: string nullable  **psi_request_status_prev**: The result of a request to PageSpeed Insights API. [Learn more](https://help.ahrefs.com/en/articles/5369589-how-to-see-core-web-vitals-and-other-speed-metrics-in-site-audit-tool)   type: string nullable  **redirect**: The destination of the redirecting URL   type: url nullable  **redirect_chain_urls**: The list of redirect chain URLs   type: array(url)  **redirect_chain_urls_code**: The list of HTTP status codes returned by the redirect chain URLs   type: array(null)  **redirect_chain_urls_no_crawl_reason**: The reasons why the redirect chain URLs were not crawled   type: array(null)  **redirect_chain_urls_no_crawl_reason_prev**: The reasons why the redirect chain URLs were not crawled   type: array(null)  **redirect_chain_urls_prev**: The list of redirect chain URLs   type: array(url)  **redirect_code**: The HTTP status code of the destination of the redirecting URL   type: integer nullable  **redirect_counts**: The number of incoming external links pointing to the URL via a redirect. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **redirect_counts_diff**: The number of incoming external links pointing to the URL via a redirect. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **redirect_counts_prev**: The number of incoming external links pointing to the URL via a redirect. Not to be confused with the number of linking pages, as one page can contain multiple backlinks   type: integer nullable  **redirect_is_canonical**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: boolean nullable  **redirect_is_canonical_prev**: Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is considered as canonical when it doesn't refer to any other pages as canonical   type: boolean nullable  **redirect_no_crawl_reason**: The reason why the destination of the redirecting URL was not crawled   type: string nullable  **redirect_no_crawl_reason_prev**: The reason why the destination of the redirecting URL was not crawled   type: string nullable  **redirect_prev**: The destination of the redirecting URL   type: url nullable  **redirect_scheme**: The protocol of the redirecting URL   type: string nullable  **redirect_scheme_prev**: The protocol of the redirecting URL   type: string nullable  **refclass_c**: The number of IP networks that have websites with at least 1 link pointing to the URL. An IP network consists of IP addresses sharing the first three numbers of their numerical label. Example: 151.80.39.61 is the website IP address where 151.80.39.XXX is the IP network   type: integer nullable  **refclass_c_diff**: The number of IP networks that have websites with at least 1 link pointing to the URL. An IP network consists of IP addresses sharing the first three numbers of their numerical label. Example: 151.80.39.61 is the website IP address where 151.80.39.XXX is the IP network   type: integer nullable  **refclass_c_prev**: The number of IP networks that have websites with at least 1 link pointing to the URL. An IP network consists of IP addresses sharing the first three numbers of their numerical label. Example: 151.80.39.61 is the website IP address where 151.80.39.XXX is the IP network   type: integer nullable  **refhosts**: The number of unique external domains that have at least 1 link pointing to the URL (data from Ahrefs' Site Explorer database)   type: integer nullable  **refhosts_diff**: The number of unique external domains that have at least 1 link pointing to the URL (data from Ahrefs' Site Explorer database)   type: integer nullable  **refhosts_prev**: The number of unique external domains that have at least 1 link pointing to the URL (data from Ahrefs' Site Explorer database)   type: integer nullable  **refips**: The number of unique external IP addresses that incorporate websites with at least 1 link pointing to the URL. Several domains can share one IP address   type: integer nullable  **refips_prev**: The number of unique external IP addresses that incorporate websites with at least 1 link pointing to the URL. Several domains can share one IP address   type: integer nullable  **refpages**: The number of unique external pages linking to the URL (data from Ahrefs' Site Explorer database)   type: integer nullable  **refpages_diff**: The number of unique external pages linking to the URL (data from Ahrefs' Site Explorer database)   type: integer nullable  **refpages_prev**: The number of unique external pages linking to the URL (data from Ahrefs' Site Explorer database)   type: integer nullable  **robots_allow_rules**: Allow: rules   type: array(null)  **robots_allow_rules_prev**: Allow: rules   type: array(null)  **robots_crawl_delay**: Crawl-delay:   type: integer nullable  **robots_crawl_delay_prev**: Crawl-delay:   type: integer nullable  **robots_disallow_rules**: Disallow: rules   type: array(null)  **robots_disallow_rules_prev**: Disallow: rules   type: array(null)  **robots_error**: The error occurred while crawling the robots.txt file   type: string nullable  **robots_error_prev**: The error occurred while crawling the robots.txt file   type: string nullable  **robots_error_text**: Robots.txt error text   type: string nullable  **robots_error_text_prev**: Robots.txt error text   type: string nullable  **robots_redirect_loop**: Robots.txt error redirect loop   type: array(null)  **robots_redirect_loop_prev**: Robots.txt error redirect loop   type: array(null)  **robots_sitemaps**: The list of sitemaps referenced in the robots.txt file   type: array(null)  **robots_sitemaps_prev**: The list of sitemaps referenced in the robots.txt file   type: array(null)  **rss**: The number of incoming external links from RSS feeds (data from Ahrefs' Site Explorer database)   type: integer nullable  **rss_diff**: The number of incoming external links from RSS feeds (data from Ahrefs' Site Explorer database)   type: integer nullable  **rss_prev**: The number of incoming external links from RSS feeds (data from Ahrefs' Site Explorer database)   type: integer nullable  **scheme**: Hypertext Transfer Protocol of the URL (HTTP or HTTPS)   type: string  **self_canonical**: Indicates that the page has a self-referential canonical URL   type: boolean nullable  **self_canonical_prev**: Indicates that the page has a self-referential canonical URL   type: boolean nullable  **self_hreflang**: Data from hreflang tag with a self-referential URL   type: array(null)  **self_hreflang_code_is_valid**: Indicates that hreflang data is specified properly in hreflang tag with a self-referential URL. The language must be specified in [ISO 639-1 format](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), and optionally the region in [ISO 3166-1 Alpha 2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)   type: array(null)  **self_hreflang_code_is_valid_prev**: Indicates that hreflang data is specified properly in hreflang tag with a self-referential URL. The language must be specified in [ISO 639-1 format](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes), and optionally the region in [ISO 3166-1 Alpha 2 format](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2)   type: array(null)  **self_hreflang_country**: The region specified in the hreflang tag with a self-referential URL   type: array(null)  **self_hreflang_country_prev**: The region specified in the hreflang tag with a self-referential URL   type: array(null)  **self_hreflang_language**: The language specified in the hreflang tag with a self-referential URL   type: array(null)  **self_hreflang_language_prev**: The language specified in the hreflang tag with a self-referential URL   type: array(null)  **self_hreflang_prev**: Data from hreflang tag with a self-referential URL   type: array(null)  **serp_title**: The title displayed for the page in its top keyword's SERP on desktop   type: string nullable  **serp_title_prev**: The title displayed for the page in its top keyword's SERP on desktop   type: string nullable  **sitemap_error**: The error occurred while crawling the sitemap   type: string nullable  **sitemap_error_prev**: The error occurred while crawling the sitemap   type: string nullable  **sitemap_error_text**: Sitemap error text   type: string nullable  **sitemap_error_text_prev**: Sitemap error text   type: string nullable  **sitemap_is_index**: Indicates that the sitemap is a sitemap index file   type: boolean nullable  **sitemap_is_index_prev**: Indicates that the sitemap is a sitemap index file   type: boolean nullable  **sitemap_nr_urls**: The number of URLs referenced in the sitemap   type: integer nullable  **sitemap_nr_urls_prev**: The number of URLs referenced in the sitemap   type: integer nullable  **sitemap_save_max_size**: Max size of sitemap allows content to be saved   type: integer nullable  **sitemap_save_max_size_diff**: Max size of sitemap allows content to be saved   type: integer nullable  **sitemap_save_max_size_prev**: Max size of sitemap allows content to be saved   type: integer nullable  **sitemap_unzipped_size**: Sitemap size (uncompressed)   type: integer nullable  **sitemap_unzipped_size_diff**: Sitemap size (uncompressed)   type: integer nullable  **sitemap_unzipped_size_prev**: Sitemap size (uncompressed)   type: integer nullable  **size**: The size of the page or resource, measured in bytes   type: integer  **size_diff**: The size of the page or resource, measured in bytes   type: integer nullable  **size_prev**: The size of the page or resource, measured in bytes   type: integer nullable  **source**: Source from which the URL can be reached   type: array(string)  **source_prev**: Source from which the URL can be reached   type: array(string)  **stamp**: The time and date when the URL was crawled   type: date  **stamp_prev**: The time and date when the URL was crawled   type: date nullable  **time_to_first_byte**: The time it takes for the crawler to receive the first byte of the response from a web server, measured in milliseconds   type: integer  **time_to_first_byte_prev**: The time it takes for the crawler to receive the first byte of the response from a web server, measured in milliseconds   type: integer nullable  **title**: The page title   type: array(string)  **title_prev**: The page title   type: array(string)  **titles_length**: The character length of the page title   type: array(integer)  **titles_length_prev**: The character length of the page title   type: array(integer)  **top_keyword**: The keyword that brings the page the most organic traffic across all countries   type: string nullable  **top_keyword_position**: The position that the page holds for its top keyword   type: integer nullable  **top_keyword_position_diff**: The position that the page holds for its top keyword   type: integer nullable  **top_keyword_position_prev**: The position that the page holds for its top keyword   type: integer nullable  **top_keyword_prev**: The keyword that brings the page the most organic traffic across all countries   type: string nullable  **traffic**: Our estimate of monthly organic search traffic coming to the URL (data from Ahrefs Site Explorer). Calculations are based on a mixture of clickstream data, the estimated monthly search volumes of keywords for which the page ranks, and the current ranking position for the URL in the search results. You can learn more [here](https://ahrefs.com/blog/ahrefs-seo-metrics/#organictraffic)   type: float nullable  **traffic_diff**: Our estimate of monthly organic search traffic coming to the URL (data from Ahrefs Site Explorer). Calculations are based on a mixture of clickstream data, the estimated monthly search volumes of keywords for which the page ranks, and the current ranking position for the URL in the search results. You can learn more [here](https://ahrefs.com/blog/ahrefs-seo-metrics/#organictraffic)   type: float nullable  **traffic_prev**: Our estimate of monthly organic search traffic coming to the URL (data from Ahrefs Site Explorer). Calculations are based on a mixture of clickstream data, the estimated monthly search volumes of keywords for which the page ranks, and the current ranking position for the URL in the search results. You can learn more [here](https://ahrefs.com/blog/ahrefs-seo-metrics/#organictraffic)   type: float nullable  **url**: The web address of the page or resource   type: url  **url_prev**: The web address of the page or resource   type: url nullable |
| `select` | `SelectStr` | No | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `filter_mode` | `FilterModeEnum` | No | Indicates which pages to return compared to the previous crawl. If not specified, all URLs that match your filter conditions are returned. `added`: URLs that are a new match for your filter conditions. `new`: URLs that are newly crawled and match your filter conditions. `removed`: URLs that stopped matching your filter conditions. `missing`: URLs that weren't crawled, but previously matched your filter conditions. `no_change`: URLs that match your filter conditions in a crawl and the crawl before it. |
| `issue_id` | `str` | No | The unique identifier of an issue. When specified, only URLs affected by this issue are returned. You can get issue IDs by querying the `site-audit/issues` endpoint. |
| `date_compared` | `str` | No | A timestamp in `YYYY-MM-DDThh:mm:ss` format specifying the crawl date to compare metrics with. Follows the same rules as the `date` field. |
| `date` | `str` | No | A timestamp in `YYYY-MM-DDThh:mm:ss` format specifying the crawl date to retrieve metrics from. Defaults to the most recent available crawl if omitted. For scheduled crawls, we return data from the latest crawl finished before the specified timestamp. For Always-on audit crawls, we return data as of the provided date and time. If the time component is omitted, it defaults to `00:00:00`. The timestamp is interpreted in UTC. |
| `project_id` | `int` | Yes | The unique identifier of the project. Only projects with verified ownership are supported. You can find the project ID in the URL of your Site Audit project in Ahrefs: `https://app.ahrefs.com/site-audit/#project_id#` |

**Returns:** `list[SiteAuditPageExplorerData]`

<details>
<summary>605 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `ai_content_level` | `str \| None` | The estimated percentage of AI-generated text on the page. Possible values: `None`, `Low`, `Moderate`, `High`, `Very ... |
| `ai_content_status` | `str \| None` | AI detection status for each page. Possible values: - `Success`: Content analyzed successfully - `Content_too_short`:... |
| `alternate` | `int \| None` | The number of incoming external links from rel="alternate" attributes on the pages (data from Ahrefs' Site Explorer d... |
| `alternate_diff` | `int \| None` | The number of incoming external links from rel="alternate" attributes on the pages (data from Ahrefs' Site Explorer d... |
| `alternate_prev` | `int \| None` | The number of incoming external links from rel="alternate" attributes on the pages (data from Ahrefs' Site Explorer d... |
| `backlinks` | `int \| None` | The number of incoming external links (both dofollow and nofollow) pointing to the URL (data from Ahrefs' Site Explor... |
| `backlinks_diff` | `int \| None` | The number of incoming external links (both dofollow and nofollow) pointing to the URL (data from Ahrefs' Site Explor... |
| `backlinks_prev` | `int \| None` | The number of incoming external links (both dofollow and nofollow) pointing to the URL (data from Ahrefs' Site Explor... |
| `canonical` | `str \| None` | The URL of the canonical version of the page |
| `canonical_code` | `int \| None` | The HTTP status code of the canonical URL |
| `canonical_counts` | `int \| None` | The number of incoming external links from canonical pages pointing to the URL. Not to be confused with the number of... |
| `canonical_counts_diff` | `int \| None` | The number of incoming external links from canonical pages pointing to the URL. Not to be confused with the number of... |
| `canonical_counts_prev` | `int \| None` | The number of incoming external links from canonical pages pointing to the URL. Not to be confused with the number of... |
| `canonical_group_hash` | `int \| None` | The ID of the group of pages that have the same canonical URL |
| `canonical_is_canonical` | `bool \| None` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `canonical_is_canonical_prev` | `bool \| None` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `canonical_no_crawl_reason` | `str \| None` | The reason why the canonical version of the page was not crawled |
| `canonical_no_crawl_reason_prev` | `str \| None` | The reason why the canonical version of the page was not crawled |
| `canonical_prev` | `str \| None` | The URL of the canonical version of the page |
| `canonical_scheme` | `str \| None` | The protocol of the canonical URL |
| `canonical_scheme_prev` | `str \| None` | The protocol of the canonical URL |
| `compliant` | `bool \| None` | Indicates that the page is indexable. An indexable page is an HTML page returning the 200 HTTP status code that has n... |
| `compliant_prev` | `bool \| None` | Indicates that the page is indexable. An indexable page is an HTML page returning the 200 HTTP status code that has n... |
| `compression` | `str \| None` | The data compression scheme |
| `compression_prev` | `str \| None` | The data compression scheme |
| `content_encoding` | `str \| None` | The Content-Encoding HTTP response header field |
| `content_encoding_prev` | `str \| None` | The Content-Encoding HTTP response header field |
| `content_length` | `int \| None` | The character length of content displayed on the page |
| `content_length_diff` | `int \| None` | The character length of content displayed on the page |
| `content_length_prev` | `int \| None` | The character length of content displayed on the page |
| `content_nr_word` | `int \| None` | The word count of content displayed on the page |
| `content_nr_word_diff` | `int \| None` | The word count of content displayed on the page |
| `content_nr_word_prev` | `int \| None` | The word count of content displayed on the page |
| `content_type` | `str \| None` | The Content-Type HTTP header of the page or resource. You can find the full list of content types [here](https://www.... |
| `content_type_prev` | `str \| None` | The Content-Type HTTP header of the page or resource. You can find the full list of content types [here](https://www.... |
| `css_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why CSS files linked from the page were not crawled |
| `css_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why CSS files linked from the page were not crawled |
| `curl_code` | `int` | CURLcode return code. You can find the full list of CURL codes [here](https://curl.haxx.se/libcurl/c/libcurl-errors.h... |
| `depth` | `int \| None` | The minimum number of clicks required for our crawler to reach the URL from the starting point of a crawl (seed page)... |
| `depth_diff` | `int \| None` | The minimum number of clicks required for our crawler to reach the URL from the starting point of a crawl (seed page)... |
| `depth_prev` | `int \| None` | The minimum number of clicks required for our crawler to reach the URL from the starting point of a crawl (seed page)... |
| `dofollow` | `int \| None` | The number of incoming external dofollow links pointing to the URL. Not to be confused with the number of linking pag... |
| `dofollow_prev` | `int \| None` | The number of incoming external dofollow links pointing to the URL. Not to be confused with the number of linking pag... |
| `domain` | `str` | The domain name part of the URL |
| `duplicate_content` | `int \| None` | The number of pages with matching or appreciably similar content |
| `duplicate_content_canonical_hreflang` | `int \| None` | The number of page groups with matching or appreciably similar content. A group includes pages united by a common can... |
| `duplicate_content_canonical_hreflang_diff` | `int \| None` | The number of page groups with matching or appreciably similar content. A group includes pages united by a common can... |
| `duplicate_content_canonical_hreflang_prev` | `int \| None` | The number of page groups with matching or appreciably similar content. A group includes pages united by a common can... |
| `duplicate_content_diff` | `int \| None` | The number of pages with matching or appreciably similar content |
| `duplicate_content_prev` | `int \| None` | The number of pages with matching or appreciably similar content |
| `duplicate_description` | `int \| None` | The number of pages that have the same meta description. If the page has more than one meta description, each will be... |
| `duplicate_description_canonical_hreflang` | `int \| None` | The number of page groups that have the same meta description. A group includes pages united by a common canonical UR... |
| `duplicate_description_canonical_hreflang_diff` | `int \| None` | The number of page groups that have the same meta description. A group includes pages united by a common canonical UR... |
| `duplicate_description_canonical_hreflang_prev` | `int \| None` | The number of page groups that have the same meta description. A group includes pages united by a common canonical UR... |
| `duplicate_description_diff` | `int \| None` | The number of pages that have the same meta description. If the page has more than one meta description, each will be... |
| `duplicate_description_prev` | `int \| None` | The number of pages that have the same meta description. If the page has more than one meta description, each will be... |
| `duplicate_group_identifier` | `int \| None` | The ID of the group of pages that are interconnected via a common canonical URL, hreflang or pagination tags |
| `duplicate_h1` | `int \| None` | The number of pages that have the same H1 subheader. If the page has more than one H1 subheader, each will be checked... |
| `duplicate_h1_diff` | `int \| None` | The number of pages that have the same H1 subheader. If the page has more than one H1 subheader, each will be checked... |
| `duplicate_h1_prev` | `int \| None` | The number of pages that have the same H1 subheader. If the page has more than one H1 subheader, each will be checked... |
| `duplicate_h1canonical_hreflang` | `int \| None` | The number of page groups sharing the same H1 subheader. A group includes pages united by a common canonical URL, hre... |
| `duplicate_h1canonical_hreflang_diff` | `int \| None` | The number of page groups sharing the same H1 subheader. A group includes pages united by a common canonical URL, hre... |
| `duplicate_h1canonical_hreflang_prev` | `int \| None` | The number of page groups sharing the same H1 subheader. A group includes pages united by a common canonical URL, hre... |
| `duplicate_title` | `int \| None` | The number of pages that have the same title. If the page has more than one title, each will be checked for duplicates |
| `duplicate_title_canonical_hreflang` | `int \| None` | The number of page groups that have the same title. A group includes pages united by a common canonical URL, hreflang... |
| `duplicate_title_canonical_hreflang_diff` | `int \| None` | The number of page groups that have the same title. A group includes pages united by a common canonical URL, hreflang... |
| `duplicate_title_canonical_hreflang_prev` | `int \| None` | The number of page groups that have the same title. A group includes pages united by a common canonical URL, hreflang... |
| `duplicate_title_diff` | `int \| None` | The number of pages that have the same title. If the page has more than one title, each will be checked for duplicates |
| `duplicate_title_prev` | `int \| None` | The number of pages that have the same title. If the page has more than one title, each will be checked for duplicates |
| `edu` | `int \| None` | The number of incoming external links from .edu domains pointing to the URL (data from Ahrefs' Site Explorer database... |
| `edu_diff` | `int \| None` | The number of incoming external links from .edu domains pointing to the URL (data from Ahrefs' Site Explorer database... |
| `edu_prev` | `int \| None` | The number of incoming external links from .edu domains pointing to the URL (data from Ahrefs' Site Explorer database... |
| `external_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by the external URLs linked from the page |
| `external_link_anchor` | `list[dict[str, Any] \| None]` | The list of anchor texts used in external outgoing links on the page |
| `external_link_anchor_prev` | `list[dict[str, Any] \| None]` | The list of anchor texts used in external outgoing links on the page |
| `external_link_domain` | `list[str \| None]` | The list of external domains linked to from the page |
| `external_link_domain_prev` | `list[str \| None]` | The list of external domains linked to from the page |
| `external_links` | `list[str \| None]` | The list of external outgoing links on the page |
| `external_links_is_canonical` | `list[dict[str, Any] \| None]` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `external_links_is_canonical_prev` | `list[dict[str, Any] \| None]` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `external_links_prev` | `list[str \| None]` | The list of external outgoing links on the page |
| `external_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why the external URLs linked from the page were not crawled |
| `external_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why the external URLs linked from the page were not crawled |
| `external_scheme` | `list[str \| None]` | The protocols of the external outgoing links on the page |
| `external_scheme_prev` | `list[str \| None]` | The protocols of the external outgoing links on the page |
| `final_redirect` | `str \| None` | The destination of the final redirecting URL |
| `final_redirect_code` | `int \| None` | The HTTP status code of the destination of the final redirecting URL |
| `final_redirect_no_crawl_reason` | `str \| None` | The reason why the destination of the final redirecting URL was not crawled |
| `final_redirect_no_crawl_reason_prev` | `str \| None` | The reason why the destination of the final redirecting URL was not crawled |
| `final_redirect_prev` | `str \| None` | The destination of the final redirecting URL |
| `found_in_sitemaps` | `list[str \| None]` | The list of sitemaps that reference the URL |
| `found_in_sitemaps_length` | `int` | The number of sitemaps that reference the URL |
| `found_in_sitemaps_prev` | `list[str \| None]` | The list of sitemaps that reference the URL |
| `gov` | `int \| None` | The total number of incoming external links from .gov domains pointing to the URL (data from Ahrefs' Site Explorer da... |
| `gov_diff` | `int \| None` | The total number of incoming external links from .gov domains pointing to the URL (data from Ahrefs' Site Explorer da... |
| `gov_prev` | `int \| None` | The total number of incoming external links from .gov domains pointing to the URL (data from Ahrefs' Site Explorer da... |
| `h1` | `list[str \| None]` | The page H1 subheader |
| `h1_prev` | `list[str \| None]` | The page H1 subheader |
| `h1length` | `list[int \| None]` | The character length of the page H1 subheader |
| `h1length_prev` | `list[int \| None]` | The character length of the page H1 subheader |
| `h2` | `list[str \| None]` | The page H2 subheader |
| `h2_prev` | `list[str \| None]` | The page H2 subheader |
| `hash_content` | `int \| None` | The page content fingerprint. Pages with matching or appreciably similar content have the same content hash |
| `hash_descriptions` | `list[int \| None]` | meta_descriptions.hash |
| `hash_h1` | `list[int \| None]` | The page H1 subheader fingerprint. Pages with matching H1 tags have the same H1 hash |
| `hash_text` | `int \| None` | The page text fingerprint. Pages with matching content have the same text hash |
| `hash_titles` | `list[int \| None]` | The page title fingerprint. Pages with matching title tags have the same title hash |
| `hreflang` | `list[dict[str, Any] \| None]` | Data from hreflang attributes |
| `hreflang_code_is_valid` | `list[dict[str, Any] \| None]` | Indicates that hreflang data is specified properly in the hreflang tags on the page. The language must be specified i... |
| `hreflang_code_is_valid_prev` | `list[dict[str, Any] \| None]` | Indicates that hreflang data is specified properly in the hreflang tags on the page. The language must be specified i... |
| `hreflang_country` | `list[dict[str, Any] \| None]` | The list of regions specified in the hreflang tags on the page |
| `hreflang_country_prev` | `list[dict[str, Any] \| None]` | The list of regions specified in the hreflang tags on the page |
| `hreflang_group_hash` | `int \| None` | The ID of the group of pages that have the same set of hreflang attributes with the same set of URLs in them |
| `hreflang_inlink_urls` | `list[str \| None]` | The list of incoming URLs with hreflang attribute |
| `hreflang_inlink_urls_prev` | `list[str \| None]` | The list of incoming URLs with hreflang attribute |
| `hreflang_issues` | `list[str \| None]` | The list of hreflang-related issues a page has |
| `hreflang_issues_prev` | `list[str \| None]` | The list of hreflang-related issues a page has |
| `hreflang_language` | `list[dict[str, Any] \| None]` | The list of languages specified in the hreflang tags on the page |
| `hreflang_language_prev` | `list[dict[str, Any] \| None]` | The list of languages specified in the hreflang tags on the page |
| `hreflang_link` | `list[str \| None]` | The list of URLs specified in the hreflang tags on the page |
| `hreflang_link_is_canonical` | `list[dict[str, Any] \| None]` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `hreflang_link_is_canonical_prev` | `list[dict[str, Any] \| None]` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `hreflang_link_prev` | `list[str \| None]` | The list of URLs specified in the hreflang tags on the page |
| `hreflang_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why URLs specified in the hreflang tags on the page were not crawled |
| `hreflang_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why URLs specified in the hreflang tags on the page were not crawled |
| `hreflang_pages_urls` | `list[str \| None]` | List of hreflang-linked pages URLs the page belongs to |
| `hreflang_pages_urls_count` | `int \| None` | Count of hreflang-linked pages URLs the page belongs to |
| `hreflang_pages_urls_count_diff` | `int \| None` | Count of hreflang-linked pages URLs the page belongs to |
| `hreflang_pages_urls_count_prev` | `int \| None` | Count of hreflang-linked pages URLs the page belongs to |
| `hreflang_pages_urls_prev` | `list[str \| None]` | List of hreflang-linked pages URLs the page belongs to |
| `hreflang_prev` | `list[dict[str, Any] \| None]` | Data from hreflang attributes |
| `html_lang` | `str \| None` | Data from the page's HTML lang tag |
| `html_lang_code_is_valid` | `bool \| None` | Indicates that the language (or language-region) code is specified properly in the HTML lang tag. The language must b... |
| `html_lang_code_is_valid_prev` | `bool \| None` | Indicates that the language (or language-region) code is specified properly in the HTML lang tag. The language must b... |
| `html_lang_country` | `str \| None` | The region code specified in the page's HTML lang tag |
| `html_lang_country_prev` | `str \| None` | The region code specified in the page's HTML lang tag |
| `html_lang_language` | `str \| None` | The language code specified in the page's HTML lang tag |
| `html_lang_language_prev` | `str \| None` | The language code specified in the page's HTML lang tag |
| `html_lang_prev` | `str \| None` | Data from the page's HTML lang tag |
| `http_code` | `int` | The HTTP status code returned by the URL |
| `http_header` | `list[str \| None]` | The HTTP headers that the web server returns |
| `http_header_prev` | `list[str \| None]` | The HTTP headers that the web server returns |
| `http_header_robots` | `list[str \| None]` | Instructions for web crawlers specified in HTTP headers |
| `http_header_robots_prev` | `list[str \| None]` | Instructions for web crawlers specified in HTTP headers |
| `http_headers_size` | `int` | The size of the HTTP headers that the web server returns, measured in bytes |
| `http_headers_size_diff` | `int \| None` | The size of the HTTP headers that the web server returns, measured in bytes |
| `http_headers_size_prev` | `int \| None` | The size of the HTTP headers that the web server returns, measured in bytes |
| `images_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why images linked from the page were not crawled |
| `images_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why images linked from the page were not crawled |
| `incoming_all_links` | `int \| None` | The number of incoming links to the URL of all types |
| `incoming_all_links_diff` | `int \| None` | The number of incoming links to the URL of all types |
| `incoming_all_links_prev` | `int \| None` | The number of incoming links to the URL of all types |
| `incoming_canonical` | `int \| None` | Shows how many times the URL is linked to from a rel="canonical" element |
| `incoming_canonical_diff` | `int \| None` | Shows how many times the URL is linked to from a rel="canonical" element |
| `incoming_canonical_prev` | `int \| None` | Shows how many times the URL is linked to from a rel="canonical" element |
| `incoming_css` | `int \| None` | The number of incoming links to the CSS file |
| `incoming_css_diff` | `int \| None` | The number of incoming links to the CSS file |
| `incoming_css_prev` | `int \| None` | The number of incoming links to the CSS file |
| `incoming_follow` | `int \| None` | The number of incoming dofollow links to the URL from hyperlinks |
| `incoming_follow_diff` | `int \| None` | The number of incoming dofollow links to the URL from hyperlinks |
| `incoming_follow_prev` | `int \| None` | The number of incoming dofollow links to the URL from hyperlinks |
| `incoming_hreflang` | `int \| None` | Shows how many times the URL is linked to from a rel="alternate" hreflang="x" attribute |
| `incoming_hreflang_diff` | `int \| None` | Shows how many times the URL is linked to from a rel="alternate" hreflang="x" attribute |
| `incoming_hreflang_prev` | `int \| None` | Shows how many times the URL is linked to from a rel="alternate" hreflang="x" attribute |
| `incoming_image` | `int \| None` | The number of incoming links to the image file |
| `incoming_image_diff` | `int \| None` | The number of incoming links to the image file |
| `incoming_image_prev` | `int \| None` | The number of incoming links to the image file |
| `incoming_js` | `int \| None` | The number of incoming links to the JS file |
| `incoming_js_diff` | `int \| None` | The number of incoming links to the JS file |
| `incoming_js_prev` | `int \| None` | The number of incoming links to the JS file |
| `incoming_links` | `int \| None` | The number of incoming links to the URL from hyperlinks |
| `incoming_links_diff` | `int \| None` | The number of incoming links to the URL from hyperlinks |
| `incoming_links_prev` | `int \| None` | The number of incoming links to the URL from hyperlinks |
| `incoming_nofollow` | `int \| None` | The number of incoming nofollow links to the URL from hyperlinks |
| `incoming_nofollow_diff` | `int \| None` | The number of incoming nofollow links to the URL from hyperlinks |
| `incoming_nofollow_prev` | `int \| None` | The number of incoming nofollow links to the URL from hyperlinks |
| `incoming_pagination` | `int \| None` | Shows how many times the URL is linked to from rel="prev" or rel="next" elements on pages |
| `incoming_pagination_diff` | `int \| None` | Shows how many times the URL is linked to from rel="prev" or rel="next" elements on pages |
| `incoming_pagination_prev` | `int \| None` | Shows how many times the URL is linked to from rel="prev" or rel="next" elements on pages |
| `incoming_redirect` | `int \| None` | The number of incoming redirecting links to the URL |
| `incoming_redirect_diff` | `int \| None` | The number of incoming redirecting links to the URL |
| `incoming_redirect_prev` | `int \| None` | The number of incoming redirecting links to the URL |
| `indexnow_error` | `str \| None` | The error description for a failed auto-submission |
| `indexnow_error_prev` | `str \| None` | The error description for a failed auto-submission |
| `indexnow_reason` | `str \| None` | The reason the page was considered for auto-submission to IndexNow |
| `indexnow_reason_prev` | `str \| None` | The reason the page was considered for auto-submission to IndexNow |
| `indexnow_status` | `str \| None` | The status of IndexNow auto-submission. Possible values:  - **Success:** The page was successfully submitted to Index... |
| `indexnow_status_prev` | `str \| None` | The status of IndexNow auto-submission. Possible values:  - **Success:** The page was successfully submitted to Index... |
| `indexnow_submitted_at` | `str \| None` | The date and time when the URL was auto-submitted to IndexNow |
| `indexnow_submitted_at_prev` | `str \| None` | The date and time when the URL was auto-submitted to IndexNow |
| `internal_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by the internal URLs linked to from the page |
| `internal_inlink_urls` | `list[str \| None]` | The list of URLs for incoming internal links |
| `internal_inlink_urls_prev` | `list[str \| None]` | The list of URLs for incoming internal links |
| `internal_link_anchor` | `list[dict[str, Any] \| None]` | The list of anchor texts used in internal outgoing links on the page |
| `internal_link_anchor_prev` | `list[dict[str, Any] \| None]` | The list of anchor texts used in internal outgoing links on the page |
| `internal_link_domain` | `list[str \| None]` | The domain (or its subdomains, depending on the scope of the crawl) linked to from internal outgoing links on the page |
| `internal_link_domain_prev` | `list[str \| None]` | The domain (or its subdomains, depending on the scope of the crawl) linked to from internal outgoing links on the page |
| `internal_links` | `list[str \| None]` | The list of internal outgoing links on the page |
| `internal_links_is_canonical` | `list[dict[str, Any] \| None]` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `internal_links_is_canonical_prev` | `list[dict[str, Any] \| None]` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `internal_links_prev` | `list[str \| None]` | The list of internal outgoing links on the page |
| `internal_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why the internal URLs linked to from the page were not crawled |
| `internal_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why the internal URLs linked to from the page were not crawled |
| `internal_scheme` | `list[str \| None]` | The protocols of the internal outgoing links on the page |
| `internal_scheme_prev` | `list[str \| None]` | The protocols of the internal outgoing links on the page |
| `is_html` | `bool` | Indicates that the content type of the web document is HTML |
| `is_in_sitemap` | `bool \| None` | Indicates that the URL is included in the website's sitemap file |
| `is_in_sitemap_prev` | `bool \| None` | Indicates that the URL is included in the website's sitemap file |
| `is_page_title_used_in_serp` | `bool \| None` | Indicates that the page and SERP titles match |
| `is_redirect_loop` | `bool \| None` | Checks if the URL has a redirect loop |
| `is_redirect_loop_prev` | `bool \| None` | Checks if the URL has a redirect loop |
| `is_rendered` | `bool \| None` | Indicates that the crawler had executed JavaScript on the page to generate content |
| `is_rendered_prev` | `bool \| None` | Indicates that the crawler had executed JavaScript on the page to generate content |
| `is_valid_internal_html` | `bool` | The HTML page on the crawled domain or its subdomain that returns a 200 HTTP status code |
| `is_valid_internal_html_prev` | `bool \| None` | The HTML page on the crawled domain or its subdomain that returns a 200 HTTP status code |
| `js_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why JavaScript files linked from the page were not crawled |
| `js_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why JavaScript files linked from the page were not crawled |
| `jsonld_attributes` | `list[str \| None]` | Names of the schema properties found on the page (with indices) |
| `jsonld_attributes_prev` | `list[str \| None]` | Names of the schema properties found on the page (with indices) |
| `jsonld_schema_types` | `list[str \| None]` | Schema objects found on the page |
| `jsonld_schema_types_prev` | `list[str \| None]` | Schema objects found on the page |
| `jsonld_validation_kinds` | `list[str \| None]` | Issues with the structured data found on the page |
| `jsonld_validation_kinds_prev` | `list[str \| None]` | Issues with the structured data found on the page |
| `jsonld_values` | `list[str \| None]` | Values of the schema properties found on the page |
| `jsonld_values_prev` | `list[str \| None]` | Values of the schema properties found on the page |
| `keywords` | `list[str \| None]` | The page meta keywords |
| `keywords_prev` | `list[str \| None]` | The page meta keywords |
| `length` | `int` | The character length of the URL |
| `links_count_css` | `int \| None` | The number of CSS files linked from the page |
| `links_count_css_prev` | `int \| None` | The number of CSS files linked from the page |
| `links_count_external` | `int \| None` | The number of external outgoing links on the page |
| `links_count_external3xx` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP stat... |
| `links_count_external3xx_diff` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP stat... |
| `links_count_external3xx_prev` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP stat... |
| `links_count_external4xx` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP sta... |
| `links_count_external4xx_diff` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP sta... |
| `links_count_external4xx_prev` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP sta... |
| `links_count_external5xx` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP sta... |
| `links_count_external5xx_diff` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP sta... |
| `links_count_external5xx_prev` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP sta... |
| `links_count_external_diff` | `int \| None` | The number of external outgoing links on the page |
| `links_count_external_follow` | `int \| None` | The number of external outgoing dofollow links on the page |
| `links_count_external_follow_diff` | `int \| None` | The number of external outgoing dofollow links on the page |
| `links_count_external_follow_prev` | `int \| None` | The number of external outgoing dofollow links on the page |
| `links_count_external_nofollow` | `int \| None` | The number of external outgoing nofollow links on the page |
| `links_count_external_nofollow_diff` | `int \| None` | The number of external outgoing nofollow links on the page |
| `links_count_external_nofollow_prev` | `int \| None` | The number of external outgoing nofollow links on the page |
| `links_count_external_non_canonical` | `int \| None` | The number of external outgoing links on the page that point to non-canonical pages |
| `links_count_external_non_canonical_diff` | `int \| None` | The number of external outgoing links on the page that point to non-canonical pages |
| `links_count_external_non_canonical_prev` | `int \| None` | The number of external outgoing links on the page that point to non-canonical pages |
| `links_count_external_prev` | `int \| None` | The number of external outgoing links on the page |
| `links_count_external_xxx` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_count_external_xxx_diff` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_count_external_xxx_prev` | `int \| None` | The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_count_images` | `int \| None` | The number of images linked from the page |
| `links_count_images_diff` | `int \| None` | The number of images linked from the page |
| `links_count_images_prev` | `int \| None` | The number of images linked from the page |
| `links_count_images_with_alt` | `int \| None` | The number of images linked from the page that have an alt attribute (alternate text) |
| `links_count_images_with_alt_diff` | `int \| None` | The number of images linked from the page that have an alt attribute (alternate text) |
| `links_count_images_with_alt_prev` | `int \| None` | The number of images linked from the page that have an alt attribute (alternate text) |
| `links_count_images_without_alt` | `int \| None` | The number of images linked from the page that have no alt attribute (alternate text) |
| `links_count_images_without_alt_diff` | `int \| None` | The number of images linked from the page that have no alt attribute (alternate text) |
| `links_count_images_without_alt_prev` | `int \| None` | The number of images linked from the page that have no alt attribute (alternate text) |
| `links_count_internal` | `int \| None` | The number of internal outgoing links on the page |
| `links_count_internal3xx` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP stat... |
| `links_count_internal3xx_diff` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP stat... |
| `links_count_internal3xx_prev` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP stat... |
| `links_count_internal4xx` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP sta... |
| `links_count_internal4xx_diff` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP sta... |
| `links_count_internal4xx_prev` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP sta... |
| `links_count_internal5xx` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP sta... |
| `links_count_internal5xx_diff` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP sta... |
| `links_count_internal5xx_prev` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP sta... |
| `links_count_internal_diff` | `int \| None` | The number of internal outgoing links on the page |
| `links_count_internal_follow` | `int \| None` | The number of internal outgoing dofollow links on the page |
| `links_count_internal_follow_diff` | `int \| None` | The number of internal outgoing dofollow links on the page |
| `links_count_internal_follow_prev` | `int \| None` | The number of internal outgoing dofollow links on the page |
| `links_count_internal_nofollow` | `int \| None` | The number of internal outgoing nofollow links on the page |
| `links_count_internal_nofollow_diff` | `int \| None` | The number of internal outgoing nofollow links on the page |
| `links_count_internal_nofollow_prev` | `int \| None` | The number of internal outgoing nofollow links on the page |
| `links_count_internal_non_canonical` | `int \| None` | The number of internal outgoing links on the page that point to non-canonical pages |
| `links_count_internal_non_canonical_diff` | `int \| None` | The number of internal outgoing links on the page that point to non-canonical pages |
| `links_count_internal_non_canonical_prev` | `int \| None` | The number of internal outgoing links on the page that point to non-canonical pages |
| `links_count_internal_prev` | `int \| None` | The number of internal outgoing links on the page |
| `links_count_internal_xxx` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_count_internal_xxx_diff` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_count_internal_xxx_prev` | `int \| None` | The number of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_count_js` | `int \| None` | The number of JavaScript files linked from the page |
| `links_count_js_diff` | `int \| None` | The number of JavaScript files linked from the page |
| `links_count_js_prev` | `int \| None` | The number of JavaScript files linked from the page |
| `links_css` | `list[str \| None]` | The list of CSS files linked from the page |
| `links_css_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by CSS files linked from the page |
| `links_css_domain` | `list[str \| None]` | The list of domains that contain CSS files linked from the page |
| `links_css_domain_prev` | `list[str \| None]` | The list of domains that contain CSS files linked from the page |
| `links_css_prev` | `list[str \| None]` | The list of CSS files linked from the page |
| `links_css_scheme` | `list[str \| None]` | The protocols of CSS files linked from the page |
| `links_css_scheme_prev` | `list[str \| None]` | The protocols of CSS files linked from the page |
| `links_external3xx` | `list[str \| None]` | The list of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status... |
| `links_external3xx_prev` | `list[str \| None]` | The list of external outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status... |
| `links_external4xx` | `list[str \| None]` | The list of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP statu... |
| `links_external4xx_prev` | `list[str \| None]` | The list of external outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP statu... |
| `links_external5xx` | `list[str \| None]` | The list of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP statu... |
| `links_external5xx_prev` | `list[str \| None]` | The list of external outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP statu... |
| `links_external_follow` | `list[str \| None]` | The list of external outgoing dofollow links on the page |
| `links_external_follow_prev` | `list[str \| None]` | The list of external outgoing dofollow links on the page |
| `links_external_nofollow` | `list[str \| None]` | The list of external outgoing nofollow links on the page |
| `links_external_nofollow_prev` | `list[str \| None]` | The list of external outgoing nofollow links on the page |
| `links_external_non_canonical` | `list[str \| None]` | The list of external outgoing links on the page that point to non-canonical pages |
| `links_external_non_canonical_prev` | `list[str \| None]` | The list of external outgoing links on the page that point to non-canonical pages |
| `links_external_xxx` | `list[str \| None]` | The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_external_xxx_prev` | `list[str \| None]` | The number of external outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx,... |
| `links_hreflang_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by the URLs specified in hreflang tags on the page |
| `links_images` | `list[str \| None]` | The list of images linked from the page |
| `links_images_alt` | `list[dict[str, Any] \| None]` | The list of alternate texts of images linked from the page |
| `links_images_alt_prev` | `list[dict[str, Any] \| None]` | The list of alternate texts of images linked from the page |
| `links_images_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by images linked from the page |
| `links_images_domain` | `list[str \| None]` | The list of domains that contain images linked from the page |
| `links_images_domain_prev` | `list[str \| None]` | The list of domains that contain images linked from the page |
| `links_images_prev` | `list[str \| None]` | The list of images linked from the page |
| `links_images_scheme` | `list[str \| None]` | The protocols of images linked from the page |
| `links_images_scheme_prev` | `list[str \| None]` | The protocols of images linked from the page |
| `links_images_with_alt` | `list[str \| None]` | The list of images linked from the page that have an alt attribute (alternate text) |
| `links_images_with_alt_prev` | `list[str \| None]` | The list of images linked from the page that have an alt attribute (alternate text) |
| `links_images_without_alt` | `list[str \| None]` | The list of images linked from the page that have no alt attribute (alternate text) |
| `links_images_without_alt_prev` | `list[str \| None]` | The list of images linked from the page that have no alt attribute (alternate text) |
| `links_internal3xx` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status... |
| `links_internal3xx_prev` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return one of the 3xx (redirection) HTTP status... |
| `links_internal4xx` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP statu... |
| `links_internal4xx_prev` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return one of the 4xx (client error) HTTP statu... |
| `links_internal5xx` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP statu... |
| `links_internal5xx_prev` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return one of the 5xx (server error) HTTP statu... |
| `links_internal_follow` | `list[str \| None]` | The list of internal outgoing dofollow links on the page |
| `links_internal_follow_prev` | `list[str \| None]` | The list of internal outgoing dofollow links on the page |
| `links_internal_nofollow` | `list[str \| None]` | The list of internal outgoing nofollow links on the page |
| `links_internal_nofollow_prev` | `list[str \| None]` | The list of internal outgoing nofollow links on the page |
| `links_internal_non_canonical` | `list[str \| None]` | The list of internal outgoing links on the page that point to non-canonical pages |
| `links_internal_non_canonical_prev` | `list[str \| None]` | The list of internal outgoing links on the page that point to non-canonical pages |
| `links_internal_xxx` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4... |
| `links_internal_xxx_prev` | `list[str \| None]` | The list of internal outgoing links on the page pointing to URLs that return HTTP status codes other than 2xx, 3xx, 4... |
| `links_js` | `list[str \| None]` | The list of JavaScript files linked from the page |
| `links_js_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by JavaScript files linked from the page |
| `links_js_domain` | `list[str \| None]` | The list of domains that contain JavaScript files linked from the page |
| `links_js_domain_prev` | `list[str \| None]` | The list of domains that contain JavaScript files linked from the page |
| `links_js_prev` | `list[str \| None]` | The list of JavaScript files linked from the page |
| `links_js_scheme` | `list[str \| None]` | The protocols of JavaScript files linked from the page |
| `links_js_scheme_prev` | `list[str \| None]` | The protocols of JavaScript files linked from the page |
| `loading_time` | `int` | The time it takes for the crawler to load the full content of the document, measured in milliseconds |
| `loading_time_diff` | `int \| None` | The time it takes for the crawler to load the full content of the document, measured in milliseconds |
| `loading_time_prev` | `int \| None` | The time it takes for the crawler to load the full content of the document, measured in milliseconds |
| `meta_description` | `list[str \| None]` | Meta description |
| `meta_description_length` | `list[int \| None]` | Meta description length |
| `meta_description_length_prev` | `list[int \| None]` | Meta description length |
| `meta_description_prev` | `list[str \| None]` | Meta description |
| `meta_refresh` | `list[str \| None]` | The time set in a meta refresh tag, in seconds |
| `meta_refresh_prev` | `list[str \| None]` | The time set in a meta refresh tag, in seconds |
| `meta_robots` | `list[str \| None]` | Instructions for web crawlers specified in HTML robots meta tags on the page |
| `meta_robots_prev` | `list[str \| None]` | Instructions for web crawlers specified in HTML robots meta tags on the page |
| `meta_twitter_tags_app_google_play` | `str \| None` | The app ID in the Google Play Store specified in the twitter:app:id:ipad meta property |
| `meta_twitter_tags_app_google_play_prev` | `str \| None` | The app ID in the Google Play Store specified in the twitter:app:id:ipad meta property |
| `meta_twitter_tags_app_ipad` | `str \| None` | The app ID in the iTunes App Store specified in the twitter:app:id:ipad meta property |
| `meta_twitter_tags_app_ipad_prev` | `str \| None` | The app ID in the iTunes App Store specified in the twitter:app:id:ipad meta property |
| `meta_twitter_tags_app_iphone` | `str \| None` | The app ID in the iTunes App Store specified in the twitter:app:id:iphone meta property |
| `meta_twitter_tags_app_iphone_prev` | `str \| None` | The app ID in the iTunes App Store specified in the twitter:app:id:iphone meta property |
| `meta_twitter_tags_attributes` | `list[str \| None]` | The list of X (Twitter) Card properties on the page |
| `meta_twitter_tags_attributes_prev` | `list[str \| None]` | The list of X (Twitter) Card properties on the page |
| `meta_twitter_tags_card` | `str \| None` | The X (Twitter) Card type can be "summary", "summary\_large\_image", "app", or "player" |
| `meta_twitter_tags_card_prev` | `str \| None` | The X (Twitter) Card type can be "summary", "summary\_large\_image", "app", or "player" |
| `meta_twitter_tags_description` | `str \| None` | meta_twitter_tags.description |
| `meta_twitter_tags_description_prev` | `str \| None` | meta_twitter_tags.description |
| `meta_twitter_tags_image` | `str \| None` | The image URL specified in the twitter:image meta property |
| `meta_twitter_tags_image_prev` | `str \| None` | The image URL specified in the twitter:image meta property |
| `meta_twitter_tags_image_url_invalid` | `bool \| None` | Indicates that the URL specified in the twitter:image meta property is a valid absolute URL |
| `meta_twitter_tags_image_url_invalid_prev` | `bool \| None` | Indicates that the URL specified in the twitter:image meta property is a valid absolute URL |
| `meta_twitter_tags_player` | `str \| None` | The HTTPS URL of player iframe specified in the twitter:player meta property |
| `meta_twitter_tags_player_height` | `int \| None` | The height of iframe in pixels specified in the twitter:player:width meta property |
| `meta_twitter_tags_player_height_diff` | `int \| None` | The height of iframe in pixels specified in the twitter:player:width meta property |
| `meta_twitter_tags_player_height_prev` | `int \| None` | The height of iframe in pixels specified in the twitter:player:width meta property |
| `meta_twitter_tags_player_prev` | `str \| None` | The HTTPS URL of player iframe specified in the twitter:player meta property |
| `meta_twitter_tags_player_width` | `int \| None` | The width of iframe in pixels specified in the twitter:player:width meta property |
| `meta_twitter_tags_player_width_diff` | `int \| None` | The width of iframe in pixels specified in the twitter:player:width meta property |
| `meta_twitter_tags_player_width_prev` | `int \| None` | The width of iframe in pixels specified in the twitter:player:width meta property |
| `meta_twitter_tags_site` | `str \| None` | The X (Twitter) handle specified in the twitter:site meta property |
| `meta_twitter_tags_site_prev` | `str \| None` | The X (Twitter) handle specified in the twitter:site meta property |
| `meta_twitter_tags_title` | `str \| None` | The title text specified in the twitter:title meta property |
| `meta_twitter_tags_title_prev` | `str \| None` | The title text specified in the twitter:title meta property |
| `meta_twitter_tags_valid` | `bool \| None` | Indicates that the page has all the necessary tags required in a X (Twitter) Card |
| `meta_twitter_tags_valid_prev` | `bool \| None` | Indicates that the page has all the necessary tags required in a X (Twitter) Card |
| `meta_twitter_tags_values` | `list[str \| None]` | Data from the X (Twitter) Card properties on the page |
| `meta_twitter_tags_values_prev` | `list[str \| None]` | Data from the X (Twitter) Card properties on the page |
| `navigation_next` | `str \| None` | The URL specified in the rel="next" element on the page |
| `navigation_next_code` | `int \| None` | The HTTP status code returned by the URL specified in the rel="next" element on a page |
| `navigation_next_no_crawl_reason` | `str \| None` | The reason why the URL specified in the rel="next" element on a page was not crawled |
| `navigation_next_no_crawl_reason_prev` | `str \| None` | The reason why the URL specified in the rel="next" element on a page was not crawled |
| `navigation_next_prev` | `str \| None` | The URL specified in the rel="next" element on the page |
| `navigation_prev_code` | `int \| None` | The HTTP status code returned by the URL specified in the rel="prev" element on a page |
| `navigation_prev_no_crawl_reason` | `str \| None` | The reason why the URL specified in the rel="prev" element on a page was not crawled |
| `navigation_prev_no_crawl_reason_prev` | `str \| None` | The reason why the URL specified in the rel="prev" element on a page was not crawled |
| `no_crawl_reason` | `str \| None` | The reason why the URL was not crawled |
| `no_crawl_reason_prev` | `str \| None` | The reason why the URL was not crawled |
| `nofollow` | `int \| None` | The number of incoming external nofollow links pointing to the URL. Not to be confused with the number of linking pag... |
| `nofollow_diff` | `int \| None` | The number of incoming external nofollow links pointing to the URL. Not to be confused with the number of linking pag... |
| `nofollow_prev` | `int \| None` | The number of incoming external nofollow links pointing to the URL. Not to be confused with the number of linking pag... |
| `nr_h1` | `int` | The number of H1 subheaders on the page |
| `nr_h1_prev` | `int \| None` | The number of H1 subheaders on the page |
| `nr_meta_description` | `int` | Number of Meta descriptions |
| `nr_meta_description_diff` | `int \| None` | Number of Meta descriptions |
| `nr_meta_description_prev` | `int \| None` | Number of Meta descriptions |
| `nr_redirect_chain_urls` | `int \| None` | The number of redirect chain URLs |
| `nr_redirect_chain_urls_diff` | `int \| None` | The number of redirect chain URLs |
| `nr_redirect_chain_urls_prev` | `int \| None` | The number of redirect chain URLs |
| `nr_titles` | `int` | The number of title tags on the page |
| `nr_titles_diff` | `int \| None` | The number of title tags on the page |
| `nr_titles_prev` | `int \| None` | The number of title tags on the page |
| `og_tags_attributes` | `list[str \| None]` | The list of Open Graph properties on a page |
| `og_tags_attributes_prev` | `list[str \| None]` | The list of Open Graph properties on a page |
| `og_tags_image` | `str \| None` | The image URL specified in the og:image meta property |
| `og_tags_image_prev` | `str \| None` | The image URL specified in the og:image meta property |
| `og_tags_image_url_invalid` | `bool \| None` | Indicates that the URL specified in the og:image meta property is a valid absolute URL |
| `og_tags_image_url_invalid_prev` | `bool \| None` | Indicates that the URL specified in the og:image meta property is a valid absolute URL |
| `og_tags_inconsistent_canonical` | `bool \| None` | Indicates that the URL specified in the og:url meta property matches the URL specified as the canonical version of th... |
| `og_tags_inconsistent_canonical_prev` | `bool \| None` | Indicates that the URL specified in the og:url meta property matches the URL specified as the canonical version of th... |
| `og_tags_title` | `str \| None` | The title text specified in the og:title meta property |
| `og_tags_title_prev` | `str \| None` | The title text specified in the og:title meta property |
| `og_tags_type` | `str \| None` | The object type specified in the og:type meta property |
| `og_tags_type_prev` | `str \| None` | The object type specified in the og:type meta property |
| `og_tags_url` | `str \| None` | The URL specified in the og:url meta property |
| `og_tags_url_prev` | `str \| None` | The URL specified in the og:url meta property |
| `og_tags_url_valid` | `bool \| None` | Indicates that the URL specified in the og:url meta property is a valid absolute URL |
| `og_tags_url_valid_prev` | `bool \| None` | Indicates that the URL specified in the og:url meta property is a valid absolute URL |
| `og_tags_valid` | `bool \| None` | Indicates that the page has all four required Open Graph properties: og:title, og:type, og:image, and og:url |
| `og_tags_valid_prev` | `bool \| None` | Indicates that the page has all four required Open Graph properties: og:title, og:type, og:image, and og:url |
| `og_tags_value` | `list[str \| None]` | Data from Open Graph properties on a page |
| `og_tags_value_prev` | `list[str \| None]` | Data from Open Graph properties on a page |
| `origin` | `str \| None` | Shows where the URL was originally found during the crawl |
| `origin_prev` | `str \| None` | Shows where the URL was originally found during the crawl |
| `page_is_nofollow` | `bool \| None` | Check if the page is nofollow, based on http header and meta robots instructions |
| `page_is_nofollow_prev` | `bool \| None` | Check if the page is nofollow, based on http header and meta robots instructions |
| `page_is_noindex` | `bool \| None` | Check if the page is noindex, based on http header and meta robots instructions |
| `page_is_noindex_prev` | `bool \| None` | Check if the page is noindex, based on http header and meta robots instructions |
| `page_rating` | `int \| None` | Page Rating (PR) shows the URL's internal and external backlink profile strength relative to other URLs included in t... |
| `page_raw_ur` | `int \| None` | URL Rating (UR) shows the strength of your target page's backlink profile on a 100-point logarithmic scale. [Learn mo... |
| `page_raw_ur_diff` | `int \| None` | URL Rating (UR) shows the strength of your target page's backlink profile on a 100-point logarithmic scale. [Learn mo... |
| `page_raw_ur_prev` | `int \| None` | URL Rating (UR) shows the strength of your target page's backlink profile on a 100-point logarithmic scale. [Learn mo... |
| `page_type` | `list[str \| None]` | Site Audit categorizes URLs as HTML Pages, Resource files (image, CSS or JavaScript), XML Sitemaps     and Robots.txt... |
| `page_type_prev` | `list[str \| None]` | Site Audit categorizes URLs as HTML Pages, Resource files (image, CSS or JavaScript), XML Sitemaps     and Robots.txt... |
| `pagination_group` | `int \| None` | The ID of the group of pages interconnected via their rel="next" and rel="prev" links |
| `pagination_group_prev` | `int \| None` | The ID of the group of pages interconnected via their rel="next" and rel="prev" links |
| `positions` | `int \| None` | The number of keywords the page is ranking for in top 100 organic search results worldwide (data from Ahrefs' Site Ex... |
| `positions_diff` | `int \| None` | The number of keywords the page is ranking for in top 100 organic search results worldwide (data from Ahrefs' Site Ex... |
| `positions_prev` | `int \| None` | The number of keywords the page is ranking for in top 100 organic search results worldwide (data from Ahrefs' Site Ex... |
| `positions_top10` | `int \| None` | The number of keywords the page is ranking for in top 10 organic search results worldwide (data from Ahrefs' Site Exp... |
| `positions_top10_diff` | `int \| None` | The number of keywords the page is ranking for in top 10 organic search results worldwide (data from Ahrefs' Site Exp... |
| `positions_top10_prev` | `int \| None` | The number of keywords the page is ranking for in top 10 organic search results worldwide (data from Ahrefs' Site Exp... |
| `positions_top3` | `int \| None` | The number of keywords the page is ranking for in top 3 organic search results worldwide (data from Ahrefs' Site Expl... |
| `positions_top3_diff` | `int \| None` | The number of keywords the page is ranking for in top 3 organic search results worldwide (data from Ahrefs' Site Expl... |
| `positions_top3_prev` | `int \| None` | The number of keywords the page is ranking for in top 3 organic search results worldwide (data from Ahrefs' Site Expl... |
| `psi_crux_cls_category` | `str \| None` | Your CLS category will be either Good (<0.1), Needs Improvement (0.1 - 0.25), or Poor (>0.25). The category is based ... |
| `psi_crux_cls_category_prev` | `str \| None` | Your CLS category will be either Good (<0.1), Needs Improvement (0.1 - 0.25), or Poor (>0.25). The category is based ... |
| `psi_crux_cls_distributions_proportion` | `list[dict[str, Any] \| None]` | What % of collected CLS metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_cls_distributions_proportion_prev` | `list[dict[str, Any] \| None]` | What % of collected CLS metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_cls_percentile` | `float \| None` | Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting.... |
| `psi_crux_cls_percentile_diff` | `int \| None` | Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting.... |
| `psi_crux_cls_percentile_prev` | `float \| None` | Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting.... |
| `psi_crux_fid_category` | `str \| None` | Your FID category will be either Good (<100 ms), Needs Improvement (100 ms - 300 ms), or Poor (>300 ms). The category... |
| `psi_crux_fid_category_prev` | `str \| None` | Your FID category will be either Good (<100 ms), Needs Improvement (100 ms - 300 ms), or Poor (>300 ms). The category... |
| `psi_crux_fid_distributions_proportion` | `list[dict[str, Any] \| None]` | What % of collected FID metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_fid_distributions_proportion_prev` | `list[dict[str, Any] \| None]` | What % of collected FID metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_fid_percentile` | `float \| None` | First Input Delay measures interactivity. This score comes from the Chrome User Experience Report which looks at real... |
| `psi_crux_fid_percentile_diff` | `int \| None` | First Input Delay measures interactivity. This score comes from the Chrome User Experience Report which looks at real... |
| `psi_crux_fid_percentile_prev` | `float \| None` | First Input Delay measures interactivity. This score comes from the Chrome User Experience Report which looks at real... |
| `psi_crux_inp_category` | `str \| None` | Your INP category will be either Good (<200 ms), Needs Improvement (200 ms - 500 ms), or Poor (>500 ms). The category... |
| `psi_crux_inp_category_prev` | `str \| None` | Your INP category will be either Good (<200 ms), Needs Improvement (200 ms - 500 ms), or Poor (>500 ms). The category... |
| `psi_crux_inp_distributions_proportion` | `list[dict[str, Any] \| None]` | What % of collected INP metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_inp_distributions_proportion_prev` | `list[dict[str, Any] \| None]` | What % of collected INP metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_inp_percentile` | `float \| None` | Interaction to Next Paint measure overall responsiveness of a page to user interactions. This score comes from the Ch... |
| `psi_crux_inp_percentile_diff` | `int \| None` | Interaction to Next Paint measure overall responsiveness of a page to user interactions. This score comes from the Ch... |
| `psi_crux_inp_percentile_prev` | `float \| None` | Interaction to Next Paint measure overall responsiveness of a page to user interactions. This score comes from the Ch... |
| `psi_crux_lcp_category` | `str \| None` | Your LCP category will be either Good (<2.5 sec), Needs Improvement (2.5 sec - 4.0 sec), or Poor (>4.0 sec). The cate... |
| `psi_crux_lcp_category_prev` | `str \| None` | Your LCP category will be either Good (<2.5 sec), Needs Improvement (2.5 sec - 4.0 sec), or Poor (>4.0 sec). The cate... |
| `psi_crux_lcp_distributions_proportion` | `list[dict[str, Any] \| None]` | What % of collected LCP metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_lcp_distributions_proportion_prev` | `list[dict[str, Any] \| None]` | What % of collected LCP metrics are in each associated threshold, which categorize performance as either "Good", "Nee... |
| `psi_crux_lcp_percentile` | `float \| None` | Largest Contentful Paint measures visual loading performance. This score comes from the Chrome User Experience Report... |
| `psi_crux_lcp_percentile_diff` | `int \| None` | Largest Contentful Paint measures visual loading performance. This score comes from the Chrome User Experience Report... |
| `psi_crux_lcp_percentile_prev` | `float \| None` | Largest Contentful Paint measures visual loading performance. This score comes from the Chrome User Experience Report... |
| `psi_lighthouse_cls_error_message` | `str \| None` | The message returned by Lighthouse if there is an error when measuring CLS |
| `psi_lighthouse_cls_error_message_prev` | `str \| None` | The message returned by Lighthouse if there is an error when measuring CLS |
| `psi_lighthouse_cls_value` | `float \| None` | Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting.... |
| `psi_lighthouse_cls_value_diff` | `int \| None` | Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting.... |
| `psi_lighthouse_cls_value_prev` | `float \| None` | Cumulative Layout Shift measures visual stability. The range is 0-1, where 0 is stable and 1 means a lot of shifting.... |
| `psi_lighthouse_lcp_error_message` | `str \| None` | The message returned by Lighthouse if there is an error when measuring LCP |
| `psi_lighthouse_lcp_error_message_prev` | `str \| None` | The message returned by Lighthouse if there is an error when measuring LCP |
| `psi_lighthouse_lcp_value` | `float \| None` | Largest Contentful Paint measures visual loading performance. This score comes from Lighthouse in a simulated test en... |
| `psi_lighthouse_lcp_value_diff` | `int \| None` | Largest Contentful Paint measures visual loading performance. This score comes from Lighthouse in a simulated test en... |
| `psi_lighthouse_lcp_value_prev` | `float \| None` | Largest Contentful Paint measures visual loading performance. This score comes from Lighthouse in a simulated test en... |
| `psi_lighthouse_score` | `int \| None` | This score uses multiple Lighthouse speed metrics to create a summary of the page's performance and use of best pract... |
| `psi_lighthouse_score_diff` | `int \| None` | This score uses multiple Lighthouse speed metrics to create a summary of the page's performance and use of best pract... |
| `psi_lighthouse_score_prev` | `int \| None` | This score uses multiple Lighthouse speed metrics to create a summary of the page's performance and use of best pract... |
| `psi_lighthouse_tbt_error_message` | `str \| None` | The message returned by Lighthouse if there is an error when measuring TBT |
| `psi_lighthouse_tbt_error_message_prev` | `str \| None` | The message returned by Lighthouse if there is an error when measuring TBT |
| `psi_lighthouse_tbt_value` | `float \| None` | Total Blocking Time measures the total amount of time that a page is blocked from responding to user interactions. Th... |
| `psi_lighthouse_tbt_value_diff` | `int \| None` | Total Blocking Time measures the total amount of time that a page is blocked from responding to user interactions. Th... |
| `psi_lighthouse_tbt_value_prev` | `float \| None` | Total Blocking Time measures the total amount of time that a page is blocked from responding to user interactions. Th... |
| `psi_mobile_issues` | `list[str \| None]` | List of mobile-related issues on the page detected by Lighthouse |
| `psi_mobile_issues_explanations` | `list[str \| None]` | Details about the mobile issues detected by Lighthouse |
| `psi_mobile_issues_explanations_prev` | `list[str \| None]` | Details about the mobile issues detected by Lighthouse |
| `psi_mobile_issues_prev` | `list[str \| None]` | List of mobile-related issues on the page detected by Lighthouse |
| `psi_request_error_message` | `str \| None` | The message returned by PageSpeed Insights API if there is an error. [Learn more](https://help.ahrefs.com/en/articles... |
| `psi_request_error_message_prev` | `str \| None` | The message returned by PageSpeed Insights API if there is an error. [Learn more](https://help.ahrefs.com/en/articles... |
| `psi_request_status` | `str \| None` | The result of a request to PageSpeed Insights API. [Learn more](https://help.ahrefs.com/en/articles/5369589-how-to-se... |
| `psi_request_status_prev` | `str \| None` | The result of a request to PageSpeed Insights API. [Learn more](https://help.ahrefs.com/en/articles/5369589-how-to-se... |
| `redirect` | `str \| None` | The destination of the redirecting URL |
| `redirect_chain_urls` | `list[str \| None]` | The list of redirect chain URLs |
| `redirect_chain_urls_code` | `list[dict[str, Any] \| None]` | The list of HTTP status codes returned by the redirect chain URLs |
| `redirect_chain_urls_no_crawl_reason` | `list[dict[str, Any] \| None]` | The reasons why the redirect chain URLs were not crawled |
| `redirect_chain_urls_no_crawl_reason_prev` | `list[dict[str, Any] \| None]` | The reasons why the redirect chain URLs were not crawled |
| `redirect_chain_urls_prev` | `list[str \| None]` | The list of redirect chain URLs |
| `redirect_code` | `int \| None` | The HTTP status code of the destination of the redirecting URL |
| `redirect_counts` | `int \| None` | The number of incoming external links pointing to the URL via a redirect. Not to be confused with the number of linki... |
| `redirect_counts_diff` | `int \| None` | The number of incoming external links pointing to the URL via a redirect. Not to be confused with the number of linki... |
| `redirect_counts_prev` | `int \| None` | The number of incoming external links pointing to the URL via a redirect. Not to be confused with the number of linki... |
| `redirect_is_canonical` | `bool \| None` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `redirect_is_canonical_prev` | `bool \| None` | Indicates whether the target page tags itself as the canonical version to be shown in search results. A page is consi... |
| `redirect_no_crawl_reason` | `str \| None` | The reason why the destination of the redirecting URL was not crawled |
| `redirect_no_crawl_reason_prev` | `str \| None` | The reason why the destination of the redirecting URL was not crawled |
| `redirect_prev` | `str \| None` | The destination of the redirecting URL |
| `redirect_scheme` | `str \| None` | The protocol of the redirecting URL |
| `redirect_scheme_prev` | `str \| None` | The protocol of the redirecting URL |
| `refclass_c` | `int \| None` | The number of IP networks that have websites with at least 1 link pointing to the URL. An IP network consists of IP a... |
| `refclass_c_diff` | `int \| None` | The number of IP networks that have websites with at least 1 link pointing to the URL. An IP network consists of IP a... |
| `refclass_c_prev` | `int \| None` | The number of IP networks that have websites with at least 1 link pointing to the URL. An IP network consists of IP a... |
| `refhosts` | `int \| None` | The number of unique external domains that have at least 1 link pointing to the URL (data from Ahrefs' Site Explorer ... |
| `refhosts_diff` | `int \| None` | The number of unique external domains that have at least 1 link pointing to the URL (data from Ahrefs' Site Explorer ... |
| `refhosts_prev` | `int \| None` | The number of unique external domains that have at least 1 link pointing to the URL (data from Ahrefs' Site Explorer ... |
| `refips` | `int \| None` | The number of unique external IP addresses that incorporate websites with at least 1 link pointing to the URL. Severa... |
| `refips_prev` | `int \| None` | The number of unique external IP addresses that incorporate websites with at least 1 link pointing to the URL. Severa... |
| `refpages` | `int \| None` | The number of unique external pages linking to the URL (data from Ahrefs' Site Explorer database) |
| `refpages_diff` | `int \| None` | The number of unique external pages linking to the URL (data from Ahrefs' Site Explorer database) |
| `refpages_prev` | `int \| None` | The number of unique external pages linking to the URL (data from Ahrefs' Site Explorer database) |
| `robots_allow_rules` | `list[dict[str, Any] \| None]` | Allow: rules |
| `robots_allow_rules_prev` | `list[dict[str, Any] \| None]` | Allow: rules |
| `robots_crawl_delay` | `int \| None` | Crawl-delay: |
| `robots_crawl_delay_prev` | `int \| None` | Crawl-delay: |
| `robots_disallow_rules` | `list[dict[str, Any] \| None]` | Disallow: rules |
| `robots_disallow_rules_prev` | `list[dict[str, Any] \| None]` | Disallow: rules |
| `robots_error` | `str \| None` | The error occurred while crawling the robots.txt file |
| `robots_error_prev` | `str \| None` | The error occurred while crawling the robots.txt file |
| `robots_error_text` | `str \| None` | Robots.txt error text |
| `robots_error_text_prev` | `str \| None` | Robots.txt error text |
| `robots_redirect_loop` | `list[dict[str, Any] \| None]` | Robots.txt error redirect loop |
| `robots_redirect_loop_prev` | `list[dict[str, Any] \| None]` | Robots.txt error redirect loop |
| `robots_sitemaps` | `list[dict[str, Any] \| None]` | The list of sitemaps referenced in the robots.txt file |
| `robots_sitemaps_prev` | `list[dict[str, Any] \| None]` | The list of sitemaps referenced in the robots.txt file |
| `rss` | `int \| None` | The number of incoming external links from RSS feeds (data from Ahrefs' Site Explorer database) |
| `rss_diff` | `int \| None` | The number of incoming external links from RSS feeds (data from Ahrefs' Site Explorer database) |
| `rss_prev` | `int \| None` | The number of incoming external links from RSS feeds (data from Ahrefs' Site Explorer database) |
| `scheme` | `str` | Hypertext Transfer Protocol of the URL (HTTP or HTTPS) |
| `self_canonical` | `bool \| None` | Indicates that the page has a self-referential canonical URL |
| `self_canonical_prev` | `bool \| None` | Indicates that the page has a self-referential canonical URL |
| `self_hreflang` | `list[dict[str, Any] \| None]` | Data from hreflang tag with a self-referential URL |
| `self_hreflang_code_is_valid` | `list[dict[str, Any] \| None]` | Indicates that hreflang data is specified properly in hreflang tag with a self-referential URL. The language must be ... |
| `self_hreflang_code_is_valid_prev` | `list[dict[str, Any] \| None]` | Indicates that hreflang data is specified properly in hreflang tag with a self-referential URL. The language must be ... |
| `self_hreflang_country` | `list[dict[str, Any] \| None]` | The region specified in the hreflang tag with a self-referential URL |
| `self_hreflang_country_prev` | `list[dict[str, Any] \| None]` | The region specified in the hreflang tag with a self-referential URL |
| `self_hreflang_language` | `list[dict[str, Any] \| None]` | The language specified in the hreflang tag with a self-referential URL |
| `self_hreflang_language_prev` | `list[dict[str, Any] \| None]` | The language specified in the hreflang tag with a self-referential URL |
| `self_hreflang_prev` | `list[dict[str, Any] \| None]` | Data from hreflang tag with a self-referential URL |
| `serp_title` | `str \| None` | The title displayed for the page in its top keyword's SERP on desktop |
| `serp_title_prev` | `str \| None` | The title displayed for the page in its top keyword's SERP on desktop |
| `sitemap_error` | `str \| None` | The error occurred while crawling the sitemap |
| `sitemap_error_prev` | `str \| None` | The error occurred while crawling the sitemap |
| `sitemap_error_text` | `str \| None` | Sitemap error text |
| `sitemap_error_text_prev` | `str \| None` | Sitemap error text |
| `sitemap_is_index` | `bool \| None` | Indicates that the sitemap is a sitemap index file |
| `sitemap_is_index_prev` | `bool \| None` | Indicates that the sitemap is a sitemap index file |
| `sitemap_nr_urls` | `int \| None` | The number of URLs referenced in the sitemap |
| `sitemap_nr_urls_prev` | `int \| None` | The number of URLs referenced in the sitemap |
| `sitemap_save_max_size` | `int \| None` | Max size of sitemap allows content to be saved |
| `sitemap_save_max_size_diff` | `int \| None` | Max size of sitemap allows content to be saved |
| `sitemap_save_max_size_prev` | `int \| None` | Max size of sitemap allows content to be saved |
| `sitemap_unzipped_size` | `int \| None` | Sitemap size (uncompressed) |
| `sitemap_unzipped_size_diff` | `int \| None` | Sitemap size (uncompressed) |
| `sitemap_unzipped_size_prev` | `int \| None` | Sitemap size (uncompressed) |
| `size` | `int` | The size of the page or resource, measured in bytes |
| `size_diff` | `int \| None` | The size of the page or resource, measured in bytes |
| `size_prev` | `int \| None` | The size of the page or resource, measured in bytes |
| `source` | `list[str \| None]` | Source from which the URL can be reached |
| `source_prev` | `list[str \| None]` | Source from which the URL can be reached |
| `stamp` | `str` | The time and date when the URL was crawled |
| `stamp_prev` | `str \| None` | The time and date when the URL was crawled |
| `time_to_first_byte` | `int` | The time it takes for the crawler to receive the first byte of the response from a web server, measured in milliseconds |
| `time_to_first_byte_prev` | `int \| None` | The time it takes for the crawler to receive the first byte of the response from a web server, measured in milliseconds |
| `title` | `list[str \| None]` | The page title |
| `title_prev` | `list[str \| None]` | The page title |
| `titles_length` | `list[int \| None]` | The character length of the page title |
| `titles_length_prev` | `list[int \| None]` | The character length of the page title |
| `top_keyword` | `str \| None` | The keyword that brings the page the most organic traffic across all countries |
| `top_keyword_position` | `int \| None` | The position that the page holds for its top keyword |
| `top_keyword_position_diff` | `int \| None` | The position that the page holds for its top keyword |
| `top_keyword_position_prev` | `int \| None` | The position that the page holds for its top keyword |
| `top_keyword_prev` | `str \| None` | The keyword that brings the page the most organic traffic across all countries |
| `traffic` | `float \| None` | Our estimate of monthly organic search traffic coming to the URL (data from Ahrefs Site Explorer). Calculations are b... |
| `traffic_diff` | `float \| None` | Our estimate of monthly organic search traffic coming to the URL (data from Ahrefs Site Explorer). Calculations are b... |
| `traffic_prev` | `float \| None` | Our estimate of monthly organic search traffic coming to the URL (data from Ahrefs Site Explorer). Calculations are b... |
| `url` | `str` | The web address of the page or resource |
| `url_prev` | `str \| None` | The web address of the page or resource |

</details>

### `site_audit_projects()`

Project Health Scores.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `date` | `str` | No | A timestamp in `YYYY-MM-DDThh:mm:ss` format specifying the crawl date to retrieve metrics from. Defaults to the most recent available crawl if omitted. For scheduled crawls, we return data from the latest crawl finished before the specified timestamp. For Always-on audit crawls, we return data as of the provided date and time. If the time component is omitted, it defaults to `00:00:00`. The timestamp is interpreted in UTC. |
| `project_id` | `int` | No | The unique identifier of the project. You can find it in the URL of your Site Audit project in Ahrefs: `https://app.ahrefs.com/site-audit/#project_id#` |

**Returns:** `list[SiteAuditProjectsData]`

| Field | Type | Description |
|-------|------|-------------|
| `project_id` | `str` | The unique identifier of the project. |
| `project_name` | `str` | The project name. |
| `target_protocol` | `str` | The protocol of the target. Possible values: `both`, `http`, `https`. |
| `target_url` | `str` | The URL of the project's target. |
| `target_mode` | `str` | The scope of the target. Possible values: `exact`, `prefix`, `domain`, `subdomains`. |
| `date` | `str \| None` | The finish date and time of the last finished crawl, in GMT time zone. |
| `status` | `str \| None` | The status of the most recent finished crawl. Possible values: `Completed`, `Stopped`, `Error`, `In_progress`. |
| `health_score` | `int \| None` | Reflects the proportion of internal URLs on your site that do not have errors, based on the last finished crawl. Excl... |
| `urls_with_errors` | `int \| None` | Number of internal URLs with errors |
| `urls_with_warnings` | `int \| None` | Number of internal URLs with warnings |
| `urls_with_notices` | `int \| None` | Number of internal URLs with notices |
| `total` | `int \| None` | Number of total crawled internal URLs |

---

## Site Explorer

### `site_explorer_all_backlinks()`

Backlinks.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See the response schema for valid column identifiers, except for `link_group_count`, which is not supported in `order_by` for this endpoint. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **ahrefs_rank_source**: The strength of the referring domain's backlink profile compared to the other websites in our database, with rank #1 being the strongest.   type: integer  **ahrefs_rank_target**: The strength of the target domain's backlink profile compared to the other websites in our database, with rank #1 being the strongest.   type: integer  **alt**: The alt attribute of the link.   type: string nullable  **anchor**: The clickable words in a link that point to a URL.   type: string  **broken_redirect_new_target**: The new destination of a modified redirect.   type: string nullable  **broken_redirect_reason**: The reason the redirect was considered broken during the last crawl.   type: string nullable   enum: `"droppedmanual"` `"droppedtooold"` `"dropped"` `"codechanged"` `"nxdomain"` `"robotsdisallowed"` `"curlerror"` `"invalidtarget"` `"nomorecanonical"` `"isnowparked"` `"targetchanged"`  **broken_redirect_source**: The redirecting URL that was modified, causing the redirect to become broken.   type: string nullable  **class_c** (5 units): The number of unique class_c subnets linking to the referring page.   type: integer  **discovered_status**: The reason the link was discovered during the last crawl: the page was crawled for the first time, the link was added to the page, or the link re-appeared after being removed.   type: string nullable   enum: `"pagefound"` `"linkfound"` `"linkrestored"`  **domain_rating_source**: The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **domain_rating_target**: The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **drop_reason**: The reason we removed the link from our index.   type: string nullable   enum: `"manual"` `"noratingunused"` `"notop"` `"tooold"` `"oldunavailable"` `"rescursive"` `"duplicate"` `"nxdomain"` `"malformed"` `"blockedport"` `"disallowed"` `"unlinked"`  **encoding**: The character set encoding of the referring page HTML.   type: string  **first_seen**: The date the referring page URL was first discovered.   type: datetime  **first_seen_link**: The date we first found a backlink to your target on a given referring page.   type: datetime  **http_code**: The return code from HTTP protocol returned during the referring page crawl.   type: integer  **http_crawl**: The link was discovered without executing javascript and rendering the page.   type: boolean  **ip_source**: The referring domain IP address.   type: string nullable  **is_alternate**: The link with the rel=“alternate” attribute.   type: boolean  **is_canonical**: The link with the rel=“canonical” attribute.   type: boolean  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_form**: The link was found in a form HTML tag.   type: boolean  **is_frame**: The link was found in an iframe HTML tag.   type: boolean  **is_homepage_link**: The link was found on the homepage of a referring website.   type: boolean  **is_image**: The link is a regular link that has an image inside their href attribute.   type: boolean  **is_lost**: The link currently does not exist anymore.   type: boolean  **is_new**: The link was discovered on the last crawl.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_redirect**: The link pointing to your target via a redirect.   type: boolean  **is_redirect_lost**: The redirected link currently does not exist anymore.   type: boolean  **is_root_source**: The referring domain name is a root domain name.   type: boolean  **is_root_target**: The target domain name is a root domain name.   type: boolean  **is_rss**: The link was found in an RSS feed.   type: boolean  **is_spam**: Indicates whether the backlink comes from a known spammy domain.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_text**: The link is a standard href hyperlink.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **js_crawl**: The link was discovered after executing javascript and rendering the page.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **last_seen**: The date we discovered that the link was lost.   type: datetime nullable  **last_visited**: The date we last verified a live link to your target page.   type: datetime  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_group_count**: The number of backlinks that were grouped together based on the aggregation parameter. This field cannot be used with aggregation 'all'.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains_source_domain**: The number of unique root domains linked from the referring domain.   type: integer  **linked_domains_source_page**: The number of unique root domains linked from the referring page.   type: integer  **linked_domains_target_domain**: The number of unique root domains linked from the target domain.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_internal**: The number of internal links from the referring page.   type: integer  **lost_reason**: The reason the link was lost during the last crawl.   type: string nullable   enum: `"removedfromhtml"` `"notcanonical"` `"noindex"` `"pageredirected"` `"pageerror"` `"lostredirect"` `"notfound"`  **name_source**: The complete referring domain name, including subdomains.   type: string  **name_target**: The complete target domain name, including subdomains.   type: string  **noindex**: The referring page has the noindex meta attribute.   type: boolean  **page_size**: The size in bytes of the referring page content.   type: integer  **port_source**: The network port of the referring page URL.   type: integer  **port_target**: The network port of the target page URL.   type: integer  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **positions_source_domain**: The number of keywords that the referring domain ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **redirect_code**: The HTTP status code of a referring page pointing to your target via a redirect.   type: integer nullable  **redirect_kind**: The HTTP status codes returned by the target redirecting URL or redirect chain.   type: array(integer)  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **refdomains_source_domain** (5 units): The number of unique referring domains linking to the referring domain.   type: integer  **refdomains_target_domain** (5 units): The number of unique referring domains linking to the target domain.   type: integer  **root_name_source**: The root domain name of the referring domain, not including subdomains.   type: string  **root_name_target**: The root domain name of the target domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **source_page_author**: The author of the referring page.   type: string nullable  **source_page_publish_date**: the date we identified the page was published   type: date nullable  **title**: The html title of the referring page.   type: string  **tld_class_source**: The top level domain class of the referring domain.   type: string   enum: `"gov"` `"edu"` `"normal"`  **tld_class_target**: The top level domain class of the target domain.   type: string   enum: `"gov"` `"edu"` `"normal"`  **traffic** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **traffic_domain** (10 units): The referring domain's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link to your target.   type: string  **url_from_plain**: The referring page URL optimized for use as a filter.   type: string  **url_rating_source**: The strength of the referring page's backlink profile compared to the others in our database on a 100-point scale.   type: float  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string  **url_to_plain**: The target page URL optimized for use as a filter.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `aggregation` | `AggregationEnum` | No | The backlinks grouping mode. |
| `history` | `str` | No | A time frame to add lost backlinks to the report. Choose between `live` (no history), `since:<date>` (history since a specified date), and `all_time` (full history). The date should be in YYYY-MM-DD format. |

**Returns:** `list[SiteExplorerAllBacklinksData]`

<details>
<summary>80 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `ahrefs_rank_source` | `int` | The strength of the referring domain's backlink profile compared to the other websites in our database, with rank #1 ... |
| `ahrefs_rank_target` | `int` | The strength of the target domain's backlink profile compared to the other websites in our database, with rank #1 bei... |
| `alt` | `str \| None` | The alt attribute of the link. |
| `anchor` | `str` | The clickable words in a link that point to a URL. |
| `broken_redirect_new_target` | `str \| None` | The new destination of a modified redirect. |
| `broken_redirect_reason` | `BrokenRedirectReasonEnum \| None` | The reason the redirect was considered broken during the last crawl. |
| `broken_redirect_source` | `str \| None` | The redirecting URL that was modified, causing the redirect to become broken. |
| `class_c` | `int` | (5 units) The number of unique class_c subnets linking to the referring page. |
| `discovered_status` | `DiscoveredStatusEnum \| None` | The reason the link was discovered during the last crawl: the page was crawled for the first time, the link was added... |
| `domain_rating_source` | `float` | The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale. |
| `domain_rating_target` | `float` | The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale. |
| `drop_reason` | `DropReasonEnum \| None` | The reason we removed the link from our index. |
| `encoding` | `str` | The character set encoding of the referring page HTML. |
| `first_seen` | `str` | The date the referring page URL was first discovered. |
| `first_seen_link` | `str` | The date we first found a backlink to your target on a given referring page. |
| `http_code` | `int` | The return code from HTTP protocol returned during the referring page crawl. |
| `http_crawl` | `bool` | The link was discovered without executing javascript and rendering the page. |
| `ip_source` | `str \| None` | The referring domain IP address. |
| `is_alternate` | `bool` | The link with the rel=“alternate” attribute. |
| `is_canonical` | `bool` | The link with the rel=“canonical” attribute. |
| `is_content` | `bool` | The link was found in the biggest piece of content on the page. |
| `is_dofollow` | `bool` | The link has no special nofollow attribute. |
| `is_form` | `bool` | The link was found in a form HTML tag. |
| `is_frame` | `bool` | The link was found in an iframe HTML tag. |
| `is_image` | `bool` | The link is a regular link that has an image inside their href attribute. |
| `is_lost` | `bool` | The link currently does not exist anymore. |
| `is_new` | `bool` | The link was discovered on the last crawl. |
| `is_nofollow` | `bool` | The link or the referring page has the nofollow attribute set. |
| `is_redirect` | `bool` | The link pointing to your target via a redirect. |
| `is_redirect_lost` | `bool` | The redirected link currently does not exist anymore. |
| `is_root_source` | `bool` | The referring domain name is a root domain name. |
| `is_root_target` | `bool` | The target domain name is a root domain name. |
| `is_rss` | `bool` | The link was found in an RSS feed. |
| `is_spam` | `bool` | Indicates whether the backlink comes from a known spammy domain. |
| `is_sponsored` | `bool` | The link has the Sponsored attribute set in the referring page HTML. |
| `is_text` | `bool` | The link is a standard href hyperlink. |
| `is_ugc` | `bool` | The link has the User Generated Content attribute set in the referring page HTML. |
| `js_crawl` | `bool` | The link was discovered after executing javascript and rendering the page. |
| `languages` | `list[str \| None]` | The languages listed in the referring page metadata or detected by the crawler to appear in the HTML. |
| `last_seen` | `str \| None` | The date we discovered that the link was lost. |
| `last_visited` | `str` | The date we last verified a live link to your target page. |
| `link_group_count` | `int` | The number of backlinks that were grouped together based on the aggregation parameter. This field cannot be used with... |
| `link_type` | `LinkTypeEnum` | The kind of the backlink. |
| `linked_domains_source_domain` | `int` | The number of unique root domains linked from the referring domain. |
| `linked_domains_source_page` | `int` | The number of unique root domains linked from the referring page. |
| `linked_domains_target_domain` | `int` | The number of unique root domains linked from the target domain. |
| `links_external` | `int` | The number of external links from the referring page. |
| `links_internal` | `int` | The number of internal links from the referring page. |
| `lost_reason` | `LostReasonEnum \| None` | The reason the link was lost during the last crawl. |
| `name_source` | `str` | The complete referring domain name, including subdomains. |
| `name_target` | `str` | The complete target domain name, including subdomains. |
| `noindex` | `bool` | The referring page has the noindex meta attribute. |
| `page_size` | `int` | The size in bytes of the referring page content. |
| `port_source` | `int` | The network port of the referring page URL. |
| `port_target` | `int` | The network port of the target page URL. |
| `positions` | `int` | The number of keywords that the referring page ranks for in the top 100 positions. |
| `powered_by` | `list[str \| None]` | Web technologies used to build and serve the referring page content. |
| `redirect_code` | `int \| None` | The HTTP status code of a referring page pointing to your target via a redirect. |
| `redirect_kind` | `list[int \| None]` | The HTTP status codes returned by the target redirecting URL or redirect chain. |
| `refdomains_source` | `int` | (5 units) The number of unique referring domains linking to the referring page. |
| `refdomains_source_domain` | `int` | (5 units) The number of unique referring domains linking to the referring domain. |
| `refdomains_target_domain` | `int` | (5 units) The number of unique referring domains linking to the target domain. |
| `root_name_source` | `str` | The root domain name of the referring domain, not including subdomains. |
| `root_name_target` | `str` | The root domain name of the target domain, not including subdomains. |
| `snippet_left` | `str` | The snippet of text appearing just before the link. |
| `snippet_right` | `str` | The snippet of text appearing just after the link. |
| `source_page_author` | `str \| None` | The author of the referring page. |
| `source_page_publish_date` | `str \| None` | the date we identified the page was published |
| `title` | `str` | The html title of the referring page. |
| `tld_class_source` | `TldClassSourceEnum` | The top level domain class of the referring domain. |
| `tld_class_target` | `TldClassSourceEnum` | The top level domain class of the target domain. |
| `traffic` | `int` | (10 units) The referring page's estimated monthly organic traffic from search. |
| `traffic_domain` | `int` | (10 units) The referring domain's estimated monthly organic traffic from search. |
| `url_from` | `str` | The URL of the page containing a link to your target. |
| `url_from_plain` | `str` | The referring page URL optimized for use as a filter. |
| `url_rating_source` | `float` | The strength of the referring page's backlink profile compared to the others in our database on a 100-point scale. |
| `url_redirect` | `list[str \| None]` | A redirect chain the target URL of the link points to. |
| `url_redirect_with_target` | `list[str \| None]` | The target URL of the link with its redirect chain. |
| `url_to` | `str` | The URL the backlink points to. |
| `url_to_plain` | `str` | The target page URL optimized for use as a filter. |

</details>

### `site_explorer_anchors()`

Anchors.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **discovered_status**: The reason the link was discovered during the last crawl: the page was crawled for the first time, the link was added to the page, or the link re-appeared after being removed.   type: string nullable   enum: `"pagefound"` `"linkfound"` `"linkrestored"`  **dofollow_links**: The number of links with a given anchor to your target that don’t have the “nofollow” attribute.   type: integer  **domain_rating**: The strength of a domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **drop_reason**: The reason we removed the link from our index.   type: string nullable   enum: `"manual"` `"noratingunused"` `"notop"` `"tooold"` `"oldunavailable"` `"rescursive"` `"duplicate"` `"nxdomain"` `"malformed"` `"blockedport"` `"disallowed"` `"unlinked"`  **first_seen**: The date we first found a link with a given anchor to your target.   type: datetime  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_homepage_link**: The link was found on the homepage of a referring website.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_root_domain**: The domain name is a root domain name.   type: boolean  **is_spam**: Indicates whether the backlink comes from a known spammy domain.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **last_seen**: The date we discovered the last backlink with a given anchor was lost.   type: datetime nullable  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains**: The number of unique root domains linked from the referring page.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_to_target**: The number of inbound backlinks your target has with a given anchor.   type: integer  **lost_links**: The number of backlinks with a given anchor lost during the selected time period.   type: integer  **lost_reason**: The reason the link was lost during the last crawl.   type: string nullable   enum: `"removedfromhtml"` `"notcanonical"` `"noindex"` `"pageredirected"` `"pageerror"` `"lostredirect"` `"notfound"`  **new_links**: The number of new backlinks with a given anchor found during the selected time period.   type: integer  **noindex**: The referring page has the noindex meta attribute.   type: boolean  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **positions_source_domain**: The number of keywords that the referring domain ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **refdomains** (5 units): The number of unique domains linking to your target with a given anchor.   type: integer  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **refpages**: The number of pages containing a link with a given anchor to your target.   type: integer  **root_domain_name**: The root domain name of the referring domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **source_page_author**: The author of the referring page.   type: string nullable  **title**: The html title of the referring page.   type: string  **top_domain_rating**: The highest Domain Rating (DR) counted out of all referring domains. DR shows the strength of a website’s backlink profile compared to the others in our database on a 100-point scale.   type: float  **traffic_domain** (10 units): The referring domain's estimated monthly organic traffic from search.   type: integer  **traffic_page** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link to your target.   type: string  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `history` | `str` | No | A time frame to add lost backlinks to the report. Choose between `live` (no history), `since:<date>` (history since a specified date), and `all_time` (full history). The date should be in YYYY-MM-DD format. |

**Returns:** `list[SiteExplorerAnchorsData]`

| Field | Type | Description |
|-------|------|-------------|
| `anchor` | `str` | The clickable words in a link that point to a URL. |
| `dofollow_links` | `int` | The number of links with a given anchor to your target that don’t have the “nofollow” attribute. |
| `first_seen` | `str` | The date we first found a link with a given anchor to your target. |
| `is_spam` | `bool` | Indicates whether the backlink comes from a known spammy domain. |
| `last_seen` | `str \| None` | The date we discovered the last backlink with a given anchor was lost. |
| `links_to_target` | `int` | The number of inbound backlinks your target has with a given anchor. |
| `lost_links` | `int` | The number of backlinks with a given anchor lost during the selected time period. |
| `new_links` | `int` | The number of new backlinks with a given anchor found during the selected time period. |
| `refdomains` | `int` | (5 units) The number of unique domains linking to your target with a given anchor. |
| `refpages` | `int` | The number of pages containing a link with a given anchor to your target. |
| `top_domain_rating` | `float` | The highest Domain Rating (DR) counted out of all referring domains. DR shows the strength of a website’s backlink pr... |

### `site_explorer_backlinks_stats()`

Backlinks stats.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |

**Returns:** `SiteExplorerBacklinksStatsData`

| Field | Type | Description |
|-------|------|-------------|
| `live` | `int` | The total number of links from other websites pointing to your target. |
| `all_time` | `int` | The total number of links from other websites pointing to your target for all time. |
| `live_refdomains` | `int` | (5 units) The total number of unique domains linking to your target. |
| `all_time_refdomains` | `int` | (5 units) The total number of unique domains linking to your target for all time. |

### `site_explorer_best_by_external_links()`

Best by External Links.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See the response schema for valid column identifiers, except for `http_code_target`, `languages_target`, `last_visited_target`, `powered_by_target`, `target_redirect`, `title_target`, `url_rating_target`, which are not supported in `order_by` for this endpoint. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **dofollow_to_target**: The number of links to your target page that don’t have the “nofollow” attribute.   type: integer  **domain_rating_source**: The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **first_seen_link**: The date we first found a link to your target.   type: datetime  **http_code_source**: The return code from HTTP protocol returned during the referring page crawl.   type: integer  **http_code_target**: The return code from HTTP protocol returned during the target page crawl.   type: integer nullable  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_homepage_link**: The link was found on the homepage of a referring website.   type: boolean  **is_lost**: The link currently does not exist anymore.   type: boolean  **is_new**: The link was discovered on the last crawl.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_root_source**: The referring domain name is a root domain name.   type: boolean  **is_spam**: Indicates whether the backlink comes from a known spammy domain.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages_source**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **languages_target**: The languages listed in the target page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **last_seen**: The date your target page lost its last live link.   type: datetime nullable  **last_visited_source**: The date we last verified a live link to your target page.   type: datetime  **last_visited_target**: The date we last crawled your target page.   type: datetime nullable  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains_source**: The number of unique root domains linked from the referring page.   type: integer  **links_external_source**: The number of external links from the referring page.   type: integer  **links_to_target**: The number of inbound backlinks the target page has.   type: integer  **lost_links_to_target**: The number of backlinks lost during the selected time period.   type: integer  **new_links_to_target**: The number of new backlinks found during the selected time period.   type: integer  **nofollow_to_target**: The number of links to your target page that have the “nofollow” attribute.   type: integer  **positions_source**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **positions_source_domain**: The number of keywords that the referring domain ranks for in the top 100 positions.   type: integer  **powered_by_source**: Web technologies used to build and serve the referring page content.   type: array(string)  **powered_by_target**: Web technologies used to build and serve the target page content.   type: array(string)  **redirects_to_target**: The number of inbound redirects to your target page.   type: integer  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **refdomains_target** (5 units): The number of unique referring domains linking to the target page.   type: integer  **root_name_source**: The root domain name of the referring domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **source_page_author**: The author of the referring page.   type: string nullable  **target_redirect**: The target's redirect if any.   type: string nullable  **title_source**: The html title of the referring page.   type: string  **title_target**: The html title of the target page.   type: string nullable  **top_domain_rating_source**: The highest Domain Rating (DR) counted out of all referring domains. DR shows the strength of a website’s backlink profile compared to the others in our database on a 100-point scale.   type: float  **traffic_domain_source** (10 units): The referring domain's estimated monthly organic traffic from search.   type: integer  **traffic_source** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from_plain**: The referring page URL optimized for use as a filter.   type: string  **url_rating_source**: The strength of the referring page's backlink profile compared to the others in our database on a 100-point scale.   type: float  **url_rating_target**: The strength of the target page's backlink profile compared to the others in our database on a 100-point scale.   type: float nullable  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string  **url_to_plain**: The target page URL optimized for use as a filter.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `history` | `str` | No | A time frame to add lost backlinks to the report. Choose between `live` (no history), `since:<date>` (history since a specified date), and `all_time` (full history). The date should be in YYYY-MM-DD format. |

**Returns:** `list[SiteExplorerBestByExternalLinksData]`

| Field | Type | Description |
|-------|------|-------------|
| `dofollow_to_target` | `int` | The number of links to your target page that don’t have the “nofollow” attribute. |
| `first_seen_link` | `str` | The date we first found a link to your target. |
| `http_code_target` | `int \| None` | The return code from HTTP protocol returned during the target page crawl. |
| `is_spam` | `bool` | Indicates whether the backlink comes from a known spammy domain. |
| `languages_target` | `list[str \| None]` | The languages listed in the target page metadata or detected by the crawler to appear in the HTML. |
| `last_seen` | `str \| None` | The date your target page lost its last live link. |
| `last_visited_source` | `str` | The date we last verified a live link to your target page. |
| `last_visited_target` | `str \| None` | The date we last crawled your target page. |
| `links_to_target` | `int` | The number of inbound backlinks the target page has. |
| `lost_links_to_target` | `int` | The number of backlinks lost during the selected time period. |
| `new_links_to_target` | `int` | The number of new backlinks found during the selected time period. |
| `nofollow_to_target` | `int` | The number of links to your target page that have the “nofollow” attribute. |
| `powered_by_target` | `list[str \| None]` | Web technologies used to build and serve the target page content. |
| `redirects_to_target` | `int` | The number of inbound redirects to your target page. |
| `refdomains_target` | `int` | (5 units) The number of unique referring domains linking to the target page. |
| `target_redirect` | `str \| None` | The target's redirect if any. |
| `title_target` | `str \| None` | The html title of the target page. |
| `top_domain_rating_source` | `float` | The highest Domain Rating (DR) counted out of all referring domains. DR shows the strength of a website’s backlink pr... |
| `url_rating_target` | `float \| None` | The strength of the target page's backlink profile compared to the others in our database on a 100-point scale. |
| `url_to` | `str` | The URL the backlink points to. |
| `url_to_plain` | `str` | The target page URL optimized for use as a filter. |

### `site_explorer_best_by_internal_links()`

Best by Internal Links.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **canonical_to_target**: The number of inbound canonical links to your target page.   type: integer  **dofollow_to_target**: The number of links to your target page that don’t have the “nofollow” attribute.   type: integer  **domain_rating_source**: The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **first_seen_link**: The date we first found a link to your target.   type: datetime  **http_code_source**: The return code from HTTP protocol returned during the referring page crawl.   type: integer  **http_code_target**: The return code from HTTP protocol returned during the target page crawl.   type: integer nullable  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_homepage_link**: The link was found on the homepage of a referring website.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_root_source**: The referring domain name is a root domain name.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages_source**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **languages_target**: The languages listed in the target page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **last_seen**: The date your target page lost its last live link.   type: datetime nullable  **last_visited_source**: The date we last verified a live link to your target page.   type: datetime  **last_visited_target**: The date we last crawled your target page.   type: datetime nullable  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains_source**: The number of unique root domains linked from the referring page.   type: integer  **links_external_source**: The number of external links from the referring page.   type: integer  **links_to_target**: The number of inbound backlinks the target page has.   type: integer  **nofollow_to_target**: The number of links to your target page that have the “nofollow” attribute.   type: integer  **positions_source**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **positions_source_domain**: The number of keywords that the referring domain ranks for in the top 100 positions.   type: integer  **powered_by_source**: Web technologies used to build and serve the referring page content.   type: array(string)  **powered_by_target**: Web technologies used to build and serve the target page content.   type: array(string)  **redirects_to_target**: The number of inbound redirects to your target page.   type: integer  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **root_name_source**: The root domain name of the referring domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **source_page_author**: The author of the referring page.   type: string nullable  **target_redirect**: The target's redirect if any.   type: string nullable  **title_source**: The html title of the referring page.   type: string  **title_target**: The html title of the target page.   type: string nullable  **traffic_domain_source** (10 units): The referring domain's estimated monthly organic traffic from search.   type: integer  **traffic_source** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from_plain**: The referring page URL optimized for use as a filter.   type: string  **url_rating_source**: The strength of the referring page's backlink profile compared to the others in our database on a 100-point scale.   type: float  **url_rating_target**: The strength of the target page's backlink profile compared to the others in our database on a 100-point scale.   type: float nullable  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string  **url_to_plain**: The target page URL optimized for use as a filter.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerBestByInternalLinksData]`

| Field | Type | Description |
|-------|------|-------------|
| `canonical_to_target` | `int` | The number of inbound canonical links to your target page. |
| `dofollow_to_target` | `int` | The number of links to your target page that don’t have the “nofollow” attribute. |
| `first_seen_link` | `str` | The date we first found a link to your target. |
| `http_code_target` | `int \| None` | The return code from HTTP protocol returned during the target page crawl. |
| `languages_target` | `list[str \| None]` | The languages listed in the target page metadata or detected by the crawler to appear in the HTML. |
| `last_seen` | `str \| None` | The date your target page lost its last live link. |
| `last_visited_source` | `str` | The date we last verified a live link to your target page. |
| `last_visited_target` | `str \| None` | The date we last crawled your target page. |
| `links_to_target` | `int` | The number of inbound backlinks the target page has. |
| `nofollow_to_target` | `int` | The number of links to your target page that have the “nofollow” attribute. |
| `powered_by_target` | `list[str \| None]` | Web technologies used to build and serve the target page content. |
| `redirects_to_target` | `int` | The number of inbound redirects to your target page. |
| `target_redirect` | `str \| None` | The target's redirect if any. |
| `title_target` | `str \| None` | The html title of the target page. |
| `url_rating_target` | `float \| None` | The strength of the target page's backlink profile compared to the others in our database on a 100-point scale. |
| `url_to` | `str` | The URL the backlink points to. |
| `url_to_plain` | `str` | The target page URL optimized for use as a filter. |

### `site_explorer_broken_backlinks()`

Broken Backlinks.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See the response schema for valid column identifiers, except for `link_group_count`, `last_visited_target`, `http_code_target`, which are not supported in `order_by` for this endpoint. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **ahrefs_rank_source**: The strength of the referring domain's backlink profile compared to the other websites in our database, with rank #1 being the strongest.   type: integer  **ahrefs_rank_target**: The strength of the target domain's backlink profile compared to the other websites in our database, with rank #1 being the strongest.   type: integer  **alt**: The alt attribute of the link.   type: string nullable  **anchor**: The clickable words in a link that point to a URL.   type: string  **class_c** (5 units): The number of unique class_c subnets linking to the referring page.   type: integer  **domain_rating_source**: The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **domain_rating_target**: The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **encoding**: The character set encoding of the referring page HTML.   type: string  **first_seen**: The date the referring page URL was first discovered.   type: datetime  **first_seen_link**: The date we first found a backlink to your target on a given referring page.   type: datetime  **http_code**: The return code from HTTP protocol returned during the referring page crawl.   type: integer  **http_code_target**: The return code from HTTP protocol returned during the target page crawl.   type: integer nullable  **http_crawl**: The link was discovered without executing javascript and rendering the page.   type: boolean  **ip_source**: The referring domain IP address.   type: string nullable  **is_alternate**: The link with the rel=“alternate” attribute.   type: boolean  **is_canonical**: The link with the rel=“canonical” attribute.   type: boolean  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_form**: The link was found in a form HTML tag.   type: boolean  **is_frame**: The link was found in an iframe HTML tag.   type: boolean  **is_homepage_link**: The link was found on the homepage of a referring website.   type: boolean  **is_image**: The link is a regular link that has an image inside their href attribute.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_redirect**: The link pointing to your target via a redirect.   type: boolean  **is_root_source**: The referring domain name is a root domain name.   type: boolean  **is_root_target**: The target domain name is a root domain name.   type: boolean  **is_rss**: The link was found in an RSS feed.   type: boolean  **is_spam**: Indicates whether the backlink comes from a known spammy domain.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_text**: The link is a standard href hyperlink.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **js_crawl**: The link was discovered after executing javascript and rendering the page.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **last_seen**: The date we discovered that the link was lost.   type: datetime nullable  **last_visited**: The date we last re-crawled the referring page to verify the backlink is alive.   type: datetime  **last_visited_target**: The date we last re-crawled the target page to verify that it is broken.   type: datetime nullable  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_group_count**: The number of backlinks that were grouped together based on the aggregation parameter. This field cannot be used with aggregation 'all'.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains_source_domain**: The number of unique root domains linked from the referring domain.   type: integer  **linked_domains_source_page**: The number of unique root domains linked from the referring page.   type: integer  **linked_domains_target_domain**: The number of unique root domains linked from the target domain.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_internal**: The number of internal links from the referring page.   type: integer  **name_source**: The complete referring domain name, including subdomains.   type: string  **name_target**: The complete target domain name, including subdomains.   type: string  **page_size**: The size in bytes of the referring page content.   type: integer  **port_source**: The network port of the referring page URL.   type: integer  **port_target**: The network port of the target page URL.   type: integer  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **positions_source_domain**: The number of keywords that the referring domain ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **redirect_code**: The HTTP status code of a referring page pointing to your target via a redirect.   type: integer nullable  **redirect_kind**: The HTTP status codes returned by the target redirecting URL or redirect chain.   type: array(integer)  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **refdomains_source_domain** (5 units): The number of unique referring domains linking to the referring domain.   type: integer  **refdomains_target_domain** (5 units): The number of unique referring domains linking to the target domain.   type: integer  **root_name_source**: The root domain name of the referring domain, not including subdomains.   type: string  **root_name_target**: The root domain name of the target domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **source_page_author**: The author of the referring page.   type: string nullable  **title**: The html title of the referring page.   type: string  **tld_class_source**: The top level domain class of the referring domain.   type: string   enum: `"gov"` `"edu"` `"normal"`  **tld_class_target**: The top level domain class of the target domain.   type: string   enum: `"gov"` `"edu"` `"normal"`  **traffic** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **traffic_domain** (10 units): The referring domain's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link to your target.   type: string  **url_from_plain**: The referring page URL optimized for use as a filter.   type: string  **url_rating_source**: The strength of the referring page's backlink profile compared to the others in our database on a 100-point scale.   type: float  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string  **url_to_plain**: The target page URL optimized for use as a filter.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `aggregation` | `AggregationEnum` | No | The backlinks grouping mode. |

**Returns:** `list[SiteExplorerBrokenBacklinksData]`

<details>
<summary>71 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `ahrefs_rank_source` | `int` | The strength of the referring domain's backlink profile compared to the other websites in our database, with rank #1 ... |
| `ahrefs_rank_target` | `int` | The strength of the target domain's backlink profile compared to the other websites in our database, with rank #1 bei... |
| `alt` | `str \| None` | The alt attribute of the link. |
| `anchor` | `str` | The clickable words in a link that point to a URL. |
| `class_c` | `int` | (5 units) The number of unique class_c subnets linking to the referring page. |
| `domain_rating_source` | `float` | The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale. |
| `domain_rating_target` | `float` | The strength of the referring domain's backlink profile compared to the others in our database on a 100-point scale. |
| `encoding` | `str` | The character set encoding of the referring page HTML. |
| `first_seen` | `str` | The date the referring page URL was first discovered. |
| `first_seen_link` | `str` | The date we first found a backlink to your target on a given referring page. |
| `http_code` | `int` | The return code from HTTP protocol returned during the referring page crawl. |
| `http_code_target` | `int \| None` | The return code from HTTP protocol returned during the target page crawl. |
| `http_crawl` | `bool` | The link was discovered without executing javascript and rendering the page. |
| `ip_source` | `str \| None` | The referring domain IP address. |
| `is_alternate` | `bool` | The link with the rel=“alternate” attribute. |
| `is_canonical` | `bool` | The link with the rel=“canonical” attribute. |
| `is_content` | `bool` | The link was found in the biggest piece of content on the page. |
| `is_dofollow` | `bool` | The link has no special nofollow attribute. |
| `is_form` | `bool` | The link was found in a form HTML tag. |
| `is_frame` | `bool` | The link was found in an iframe HTML tag. |
| `is_image` | `bool` | The link is a regular link that has an image inside their href attribute. |
| `is_nofollow` | `bool` | The link or the referring page has the nofollow attribute set. |
| `is_redirect` | `bool` | The link pointing to your target via a redirect. |
| `is_root_source` | `bool` | The referring domain name is a root domain name. |
| `is_root_target` | `bool` | The target domain name is a root domain name. |
| `is_rss` | `bool` | The link was found in an RSS feed. |
| `is_spam` | `bool` | Indicates whether the backlink comes from a known spammy domain. |
| `is_sponsored` | `bool` | The link has the Sponsored attribute set in the referring page HTML. |
| `is_text` | `bool` | The link is a standard href hyperlink. |
| `is_ugc` | `bool` | The link has the User Generated Content attribute set in the referring page HTML. |
| `js_crawl` | `bool` | The link was discovered after executing javascript and rendering the page. |
| `languages` | `list[str \| None]` | The languages listed in the referring page metadata or detected by the crawler to appear in the HTML. |
| `last_seen` | `str \| None` | The date we discovered that the link was lost. |
| `last_visited` | `str` | The date we last re-crawled the referring page to verify the backlink is alive. |
| `last_visited_target` | `str \| None` | The date we last re-crawled the target page to verify that it is broken. |
| `link_group_count` | `int` | The number of backlinks that were grouped together based on the aggregation parameter. This field cannot be used with... |
| `link_type` | `LinkTypeEnum` | The kind of the backlink. |
| `linked_domains_source_domain` | `int` | The number of unique root domains linked from the referring domain. |
| `linked_domains_source_page` | `int` | The number of unique root domains linked from the referring page. |
| `linked_domains_target_domain` | `int` | The number of unique root domains linked from the target domain. |
| `links_external` | `int` | The number of external links from the referring page. |
| `links_internal` | `int` | The number of internal links from the referring page. |
| `name_source` | `str` | The complete referring domain name, including subdomains. |
| `name_target` | `str` | The complete target domain name, including subdomains. |
| `page_size` | `int` | The size in bytes of the referring page content. |
| `port_source` | `int` | The network port of the referring page URL. |
| `port_target` | `int` | The network port of the target page URL. |
| `positions` | `int` | The number of keywords that the referring page ranks for in the top 100 positions. |
| `powered_by` | `list[str \| None]` | Web technologies used to build and serve the referring page content. |
| `redirect_code` | `int \| None` | The HTTP status code of a referring page pointing to your target via a redirect. |
| `redirect_kind` | `list[int \| None]` | The HTTP status codes returned by the target redirecting URL or redirect chain. |
| `refdomains_source` | `int` | (5 units) The number of unique referring domains linking to the referring page. |
| `refdomains_source_domain` | `int` | (5 units) The number of unique referring domains linking to the referring domain. |
| `refdomains_target_domain` | `int` | (5 units) The number of unique referring domains linking to the target domain. |
| `root_name_source` | `str` | The root domain name of the referring domain, not including subdomains. |
| `root_name_target` | `str` | The root domain name of the target domain, not including subdomains. |
| `snippet_left` | `str` | The snippet of text appearing just before the link. |
| `snippet_right` | `str` | The snippet of text appearing just after the link. |
| `source_page_author` | `str \| None` | The author of the referring page. |
| `title` | `str` | The html title of the referring page. |
| `tld_class_source` | `TldClassSourceEnum` | The top level domain class of the referring domain. |
| `tld_class_target` | `TldClassSourceEnum` | The top level domain class of the target domain. |
| `traffic` | `int` | (10 units) The referring page's estimated monthly organic traffic from search. |
| `traffic_domain` | `int` | (10 units) The referring domain's estimated monthly organic traffic from search. |
| `url_from` | `str` | The URL of the page containing a link to your target. |
| `url_from_plain` | `str` | The referring page URL optimized for use as a filter. |
| `url_rating_source` | `float` | The strength of the referring page's backlink profile compared to the others in our database on a 100-point scale. |
| `url_redirect` | `list[str \| None]` | A redirect chain the target URL of the link points to. |
| `url_redirect_with_target` | `list[str \| None]` | The target URL of the link with its redirect chain. |
| `url_to` | `str` | The URL the backlink points to. |
| `url_to_plain` | `str` | The target page URL optimized for use as a filter. |

</details>

### `site_explorer_domain_rating()`

Domain rating.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |

**Returns:** `SiteExplorerDomainRatingData`

| Field | Type | Description |
|-------|------|-------------|
| `domain_rating` | `float` | The strength of your target's backlink profile compared to the other websites in our database on a 100-point logarith... |
| `ahrefs_rank` | `int \| None` | The strength of your target's backlink profile compared to the other websites in our database, with rank #1 being the... |

### `site_explorer_domain_rating_history()`

Domain Rating history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |

**Returns:** `list[SiteExplorerDomainRatingHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `domain_rating` | `float` | The strength of your target page's backlink profile compared to the other websites in our database on a 100-point log... |

### `site_explorer_keywords_history()`

Keywords history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `select` | `SelectStr` | No | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerKeywordsHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `top11_20` | `int` | The total number of keywords that your target ranks for in the top 11-20 organic search results. |
| `top11_plus` | `int` | The total number of keywords that your target ranks for in the top 11+ organic search results. |
| `top21_50` | `int` | The total number of keywords that your target ranks for in the top 21-50 organic search results. |
| `top3` | `int` | The total number of keywords that your target ranks for in the top 3 organic search results. |
| `top4_10` | `int` | The total number of keywords that your target ranks for in the top 4-10 organic search results. |
| `top51_plus` | `int` | The total number of keywords that your target ranks for in the top 51+ organic search results. |

### `site_explorer_linked_anchors_external()`

Outgoing external anchors.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **dofollow_links**: The number of outbound links with a given anchor from your target that don’t have the “nofollow” attribute.   type: integer  **domain**: A linked domain that has at least one link from your target with a given anchor.   type: string  **domain_rating**: The strength of a domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **first_seen**: The date we first found a link with a given anchor on your target.   type: datetime  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains**: The number of unique domains linked from your target with a given anchor.   type: integer  **linked_domains_source**: The number of unique root domains linked from the source page.   type: integer  **linked_pages**: The number of unique pages linked from your target with a given anchor.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_from_target**: The number of outbound links your target has with a given anchor.   type: integer  **port_source**: The network port of the referring page URL.   type: integer  **port_target**: The network port of the target page URL.   type: integer  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **title**: The html title of the referring page.   type: string  **traffic_page** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link to your target.   type: string  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerLinkedAnchorsExternalData]`

| Field | Type | Description |
|-------|------|-------------|
| `anchor` | `str` | The clickable words in a link that point to a URL. |
| `dofollow_links` | `int` | The number of outbound links with a given anchor from your target that don’t have the “nofollow” attribute. |
| `first_seen` | `str` | The date we first found a link with a given anchor on your target. |
| `linked_domains` | `int` | The number of unique domains linked from your target with a given anchor. |
| `linked_pages` | `int` | The number of unique pages linked from your target with a given anchor. |
| `links_from_target` | `int` | The number of outbound links your target has with a given anchor. |

### `site_explorer_linked_anchors_internal()`

Outgoing internal anchors.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **dofollow_links**: The number of outbound links with a given anchor from your target that don’t have the “nofollow” attribute.   type: integer  **domain**: A linked domain that has at least one link from your target with a given anchor.   type: string  **domain_rating**: The strength of a domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **first_seen**: The date we first found a link with a given anchor on your target.   type: datetime  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains_source**: The number of unique root domains linked from the source page.   type: integer  **linked_pages**: The number of unique pages linked from your target with a given anchor.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_from_target**: The number of outbound links your target has with a given anchor.   type: integer  **port_source**: The network port of the referring page URL.   type: integer  **port_target**: The network port of the target page URL.   type: integer  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **refdomains_source** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **title**: The html title of the referring page.   type: string  **traffic_page** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link to your target.   type: string  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerLinkedAnchorsInternalData]`

| Field | Type | Description |
|-------|------|-------------|
| `anchor` | `str` | The clickable words in a link that point to a URL. |
| `dofollow_links` | `int` | The number of outbound links with a given anchor from your target that don’t have the “nofollow” attribute. |
| `first_seen` | `str` | The date we first found a link with a given anchor on your target. |
| `linked_pages` | `int` | The number of unique pages linked from your target with a given anchor. |
| `links_from_target` | `int` | The number of outbound links your target has with a given anchor. |

### `site_explorer_linkeddomains()`

Linked Domains.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **dofollow_linked_domains**: The number of unique root domains with dofollow links linked from the linked domain.   type: integer  **dofollow_links**: The number of links from your target to the linked domain that don’t have the “nofollow” attribute.   type: integer  **dofollow_refdomains** (5 units): The number of unique domains with dofollow links to the linked domain.   type: integer  **domain**: A linked domain that has at least one link from your target.   type: string  **domain_rating**: The strength of a domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **first_seen**: The date we first found a link to the linked domain from your target.   type: datetime  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_root_domain**: The domain name is a root domain name.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domain_traffic** (10 units): The linked domain’s estimated monthly organic traffic from search   type: integer  **linked_domains**: The number of unique root domains linked from the referring page.   type: integer  **linked_pages**: The number of the domain's pages linked from your target.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_from_target**: The number of links to the linked domain from your target.   type: integer  **port_source**: The network port of the referring page URL.   type: integer  **port_target**: The network port of the target page URL.   type: integer  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **refdomains** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **root_domain_name**: The root domain name of the referring domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **title**: The html title of the referring page.   type: string  **traffic_page** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link from your target.   type: string  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the outgoing link points to.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerLinkeddomainsData]`

| Field | Type | Description |
|-------|------|-------------|
| `dofollow_linked_domains` | `int` | The number of unique root domains with dofollow links linked from the linked domain. |
| `dofollow_links` | `int` | The number of links from your target to the linked domain that don’t have the “nofollow” attribute. |
| `dofollow_refdomains` | `int` | (5 units) The number of unique domains with dofollow links to the linked domain. |
| `domain` | `str` | A linked domain that has at least one link from your target. |
| `domain_rating` | `float` | The strength of a domain's backlink profile compared to the others in our database on a 100-point scale. |
| `first_seen` | `str` | The date we first found a link to the linked domain from your target. |
| `is_root_domain` | `bool` | The domain name is a root domain name. |
| `linked_domain_traffic` | `int` | (10 units) The linked domain’s estimated monthly organic traffic from search |
| `linked_pages` | `int` | The number of the domain's pages linked from your target. |
| `links_from_target` | `int` | The number of links to the linked domain from your target. |

### `site_explorer_metrics()`

Metrics.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |

**Returns:** `SiteExplorerMetricsData`

| Field | Type | Description |
|-------|------|-------------|
| `org_keywords` | `int` | The total number of keywords that your target ranks for in the top 100 organic search results. |
| `paid_keywords` | `int` | The total number of keywords that your target ranks for in paid search results. |
| `org_keywords_1_3` | `int` | The total number of keywords that your target ranks for in the top 3 organic search results. |
| `org_traffic` | `int` | (10 units) The estimated number of monthly visitors that your target gets from organic search. |
| `org_cost` | `int \| None` | (10 units) The estimated value of your target's monthly organic search traffic, in USD cents. |
| `paid_traffic` | `int` | (10 units) The estimated number of monthly visitors that your target gets from paid search. |
| `paid_cost` | `int \| None` | (10 units) The estimated cost of your target's monthly paid search traffic, in USD cents. |
| `paid_pages` | `int` | The total number of pages from a target ranking in paid search results. |

### `site_explorer_metrics_by_country()`

Metrics by country.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `select` | `SelectStr` | No | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |

**Returns:** `list[SiteExplorerMetricsByCountryData]`

| Field | Type | Description |
|-------|------|-------------|
| `country` | `CountryEnum1` |  |
| `org_cost` | `int \| None` | (10 units) The estimated value of your target's monthly organic search traffic, in USD cents. |
| `org_keywords` | `int` | The total number of keywords that your target ranks for in the top 100 organic search results. |
| `org_keywords_1_3` | `int` | The total number of keywords that your target ranks for in the top 3 organic search results. |
| `org_traffic` | `int` | (10 units) The estimated number of monthly visitors that your target gets from organic search. |
| `paid_cost` | `int \| None` | (10 units) The estimated cost of your target's monthly paid search traffic, in USD cents. |
| `paid_keywords` | `int` | The total number of keywords that your target ranks for in paid search results. |
| `paid_pages` | `int` | The total number of pages from a target ranking in the top 100 paid search results. |
| `paid_traffic` | `int` | (10 units) The estimated number of monthly visitors that your target gets from paid search. |

### `site_explorer_metrics_history()`

Metrics history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `select` | `SelectStr` | No | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerMetricsHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `org_cost` | `int` | (10 units) The estimated cost of your target's monthly organic search traffic, in USD cents. |
| `org_traffic` | `int` | (10 units) The estimated number of monthly visitors that your target gets from organic search. |
| `paid_cost` | `int` | (10 units) The estimated cost of your target's monthly paid search traffic, in USD cents. |
| `paid_traffic` | `int` | (10 units) The estimated number of monthly visitors that your target gets from paid search. |

### `site_explorer_organic_competitors()`

Organic competitors.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **competitor_domain**: A competitor's domain of your target in “domains" group mode.   type: domain nullable  **competitor_url**: A competitor's URL of your target in pages" group mode.   type: url nullable  **cpc_competitor**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents for a competitor.   type: integer nullable  **cpc_target**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents for a target.   type: integer nullable  **domain_rating**: The strength of a domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **group_mode**: To see competing pages instead, use the “exact URL” target mode or “path” target mode if your target doesn't have multiple pages.   type: string   enum: `"domains"` `"pages"`  **keyword_difficulty_competitor** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale for a competitor.   type: integer nullable  **keyword_difficulty_target** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale for a target.   type: integer nullable  **keywords_common**: Organic keywords that both your target and a competitor are ranking for.   type: integer  **keywords_competitor**: Organic keywords that a competitor is ranking for, but your target isn't.   type: integer  **keywords_target**: Organic keywords that your target is ranking for, but a competitor isn't.   type: integer  **pages**: The total number of pages from a target ranking in search results.   type: integer nullable  **pages_diff**: The change in pages between your selected dates.   type: integer  **pages_merged**: The pages field optimized for sorting.   type: integer  **pages_prev**: The total number of pages from a target ranking in search results on the comparison date.   type: integer nullable  **share**: The percentage of common keywords out of the total number of keywords that your target and a competitor both rank for.   type: float  **traffic** (10 units): An estimation of the number of monthly visits that a page gets from organic search over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable  **traffic_diff**: The change in traffic between your selected dates.   type: integer  **traffic_merged** (10 units): The traffic field optimized for sorting.   type: integer  **traffic_prev** (10 units): An estimation of the number of monthly visits that a page gets from organic search over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter on the comparison date.   type: integer nullable  **value** (10 units): The estimated value of a page's monthly organic search traffic, in USD cents.   type: integer nullable  **value_diff**: The change in value between your selected dates.   type: integer  **value_merged** (10 units): The value field optimized for sorting.   type: integer nullable  **value_prev** (10 units): The estimated value of a page's monthly organic search traffic, in USD cents on the comparison date.   type: integer nullable  **volume_competitor** (10 units): An estimation of the average monthly number of searches for a keyword over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter for a competitor.   type: integer nullable  **volume_target** (10 units): An estimation of the average monthly number of searches for a keyword over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter for a target.   type: integer nullable  **words_competitor**: The number of words in a keyword for a competitor.   type: integer  **words_target**: The number of words in a keyword for a target.   type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `country` | `CountryEnum` | Yes | A two-letter country code (ISO 3166-1 alpha-2). |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[SiteExplorerOrganicCompetitorsData]`

| Field | Type | Description |
|-------|------|-------------|
| `competitor_domain` | `str \| None` | A competitor's domain of your target in “domains" group mode. |
| `competitor_url` | `str \| None` | A competitor's URL of your target in pages" group mode. |
| `domain_rating` | `float` | The strength of a domain's backlink profile compared to the others in our database on a 100-point scale. |
| `group_mode` | `GroupModeEnum` | To see competing pages instead, use the “exact URL” target mode or “path” target mode if your target doesn't have mul... |
| `keywords_common` | `int` | Organic keywords that both your target and a competitor are ranking for. |
| `keywords_competitor` | `int` | Organic keywords that a competitor is ranking for, but your target isn't. |
| `keywords_target` | `int` | Organic keywords that your target is ranking for, but a competitor isn't. |
| `pages` | `int \| None` | The total number of pages from a target ranking in search results. |
| `pages_diff` | `int` | The change in pages between your selected dates. |
| `pages_merged` | `int` | The pages field optimized for sorting. |
| `pages_prev` | `int \| None` | The total number of pages from a target ranking in search results on the comparison date. |
| `share` | `float` | The percentage of common keywords out of the total number of keywords that your target and a competitor both rank for. |
| `traffic` | `int \| None` | (10 units) An estimation of the number of monthly visits that a page gets from organic search over the latest month o... |
| `traffic_diff` | `int` | The change in traffic between your selected dates. |
| `traffic_merged` | `int` | (10 units) The traffic field optimized for sorting. |
| `traffic_prev` | `int \| None` | (10 units) An estimation of the number of monthly visits that a page gets from organic search over the latest month o... |
| `value` | `int \| None` | (10 units) The estimated value of a page's monthly organic search traffic, in USD cents. |
| `value_diff` | `int` | The change in value between your selected dates. |
| `value_merged` | `int \| None` | (10 units) The value field optimized for sorting. |
| `value_prev` | `int \| None` | (10 units) The estimated value of a page's monthly organic search traffic, in USD cents on the comparison date. |

### `site_explorer_organic_keywords()`

Organic keywords.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **best_position**: The top position your target ranks for in the organic search results for a keyword.   type: integer nullable  **best_position_diff**: The change in position between your selected dates.   type: integer nullable  **best_position_has_thumbnail**: The top position has a thumbnail.   type: boolean nullable  **best_position_has_thumbnail_prev**: The top position has a thumbnail on the comparison date.   type: boolean nullable  **best_position_has_video**: The top position has a video.   type: boolean nullable  **best_position_has_video_prev**: The top position has a video on the comparison date.   type: boolean nullable  **best_position_kind**: The kind of the top position: organic, paid, or a SERP feature.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **best_position_kind_merged**: The kind of the top position optimized for sorting.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **best_position_kind_prev**: The kind of the top position on the comparison date.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **best_position_prev**: The top position on the comparison date.   type: integer nullable  **best_position_set**: The ranking group of the top position.   type: string   enum: `"top_3"` `"top_4_10"` `"top_11_50"` `"top_51_more"`  **best_position_set_prev**: The ranking group of the top position on the comparison date.   type: string nullable   enum: `"top_3"` `"top_4_10"` `"top_11_50"` `"top_51_more"`  **best_position_url**: The ranking URL in organic search results.   type: string nullable  **best_position_url_prev**: The ranking URL on the comparison date.   type: string nullable  **best_position_url_raw**: The ranking page URL in encoded format.   type: string nullable  **best_position_url_raw_prev**: The ranking page URL on the comparison date in encoded format.   type: string nullable  **cpc**: Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, in USD cents.   type: integer nullable  **cpc_merged**: The CPC field optimized for sorting.   type: integer nullable  **cpc_prev**: The CPC metric on the comparison date.   type: integer nullable  **entities**: Organizations, products, persons, works, events, and locations found in a keyword.   type: array(object)  **event_entities**: Events found in a keyword.   type: array(string)  **is_best_position_set_top_11_50**: The ranking group of the top position is 11-50.   type: boolean  **is_best_position_set_top_11_50_prev**: The ranking group of the top position was 11-50 on the comparison date.   type: boolean nullable  **is_best_position_set_top_3**: The ranking group of the top position is Top 3.   type: boolean  **is_best_position_set_top_3_prev**: The ranking group of the top position was Top 3 on the comparison date.   type: boolean nullable  **is_best_position_set_top_4_10**: The ranking group of the top position is 4-10.   type: boolean  **is_best_position_set_top_4_10_prev**: The ranking group of the top position was 4-10 on the comparison date.   type: boolean nullable  **is_branded**: User intent: branded. The user is searching for a specific brand or company name.   type: boolean  **is_commercial**: User intent: commercial. The user is comparing products or services before making a purchase decision.   type: boolean  **is_informational**: User intent: informational. The user is looking for information or an answer to a specific question.   type: boolean  **is_local**: User intent: local. The user is looking for information relevant to a specific location or nearby services.   type: boolean  **is_main_position**: Excludes positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter).   type: boolean  **is_main_position_prev**: Excludes positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter) on the comparison date.   type: boolean  **is_navigational**: User intent: navigational. The user is searching for a specific website or web page.   type: boolean  **is_transactional**: User intent: transactional. The user is ready to complete an action, often a purchase.   type: boolean  **keyword**: The keyword your target ranks for.   type: string  **keyword_country**: The country of a keyword your target ranks for.   type: string   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **keyword_difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **keyword_difficulty_merged** (10 units): The keyword difficulty field optimized for sorting.   type: integer nullable  **keyword_difficulty_prev** (10 units): The keyword difficulty on the comparison date.   type: integer nullable  **keyword_merged**: The keyword field optimized for sorting.   type: string  **keyword_prev**: The keyword your target ranks for on the comparison date.   type: string  **language**: The SERP language.   type: string  **language_prev**: The SERP language on the comparison date.   type: string nullable  **last_update**: The date when we last checked search engine results for a keyword.   type: datetime  **last_update_prev**: The date when we checked search engine results up to the comparison date.   type: datetime nullable  **location_entities**: Locations found in a keyword.   type: array(string)  **organisation_entities**: Organizations found in a keyword.   type: array(string)  **person_entities**: Persons found in a keyword.   type: array(string)  **position_kind**: The kind of a position: organic, paid or a SERP feature. This applies to all positions for a given keyword and URL before picking the top position.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **position_kind_prev**: The kind of a position on the comparison date.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **positions_kinds**: The kinds of the top positions.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **positions_kinds_prev**: The kinds of the top positions on the comparison date.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **product_entities**: Products found in a keyword.   type: array(string)  **serp_features**: The SERP features that appear in search results for a keyword.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_features_count**: The number of SERP features that appear in search results for a keyword.   type: integer  **serp_features_count_prev**: The number of SERP features on the comparison date.   type: integer nullable  **serp_features_merged**: The SERP features field optimized for sorting.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_features_prev**: The SERP features that appear in search results for a keyword on the comparison date.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_target_main_positions_count**: The number of target URLs ranking for a keyword excluding positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter).   type: integer  **serp_target_main_positions_count_prev**: The number of target URLs ranking for a keyword excluding positions in Sitelinks, Top stories, Image packs, and posts on X (Twitter) on the comparison date.   type: integer nullable  **serp_target_positions_count**: The number of target URLs ranking for a keyword.   type: integer  **serp_target_positions_count_prev**: The number of target URLs ranking for a keyword on the comparison date.   type: integer nullable  **status**: The status of a page: the new page that just started to rank ("left"), the lost page that disappeared from search results ("right"), or no change ("both").   type: string   enum: `"left"` `"right"` `"both"`  **sum_paid_traffic** (10 units): An estimation of the number of monthly visits that your target gets from paid search for a keyword.   type: integer nullable  **sum_paid_traffic_merged** (10 units): The paid traffic field optimized for sorting.   type: integer  **sum_paid_traffic_prev** (10 units): The paid traffic on the comparison date.   type: integer nullable  **sum_traffic** (10 units): An estimation of the number of monthly visitors that your target gets from organic search for a keyword.   type: integer nullable  **sum_traffic_merged** (10 units): The traffic field optimized for sorting.   type: integer  **sum_traffic_prev** (10 units): The traffic on the comparison date.   type: integer nullable  **title**: The title displayed for the page in a keyword's SERP.   type: string  **title_prev**: The title displayed for the page in a keyword's SERP on the comparison date.   type: string  **volume** (10 units): An estimation of the number of searches for a keyword over the latest month.   type: integer nullable  **volume_desktop_pct**: The percentage of the total search volume that comes from desktop devices.   type: float nullable  **volume_merged** (10 units): The search volume field optimized for sorting.   type: integer nullable  **volume_mobile_pct**: The percentage of the total search volume that comes from mobile devices.   type: float nullable  **volume_prev** (10 units): The search volume on the comparison date.   type: integer nullable  **words**: The number of words in a keyword.   type: integer  **words_merged**: The number of words in a keyword optimized for sorting.   type: integer  **words_prev**: The number of words in a keyword on the comparison date.   type: integer  **work_entities**: Works found in a keyword.   type: array(string) |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[SiteExplorerOrganicKeywordsData]`

<details>
<summary>67 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `all_positions` | `list[dict[str, Any] \| None]` | (5 units) The list of all positions for a keyword. |
| `all_positions_prev` | `list[dict[str, Any] \| None]` | (5 units) The list of all positions for a keyword on the comparison date. |
| `best_position` | `int \| None` | The top position your target ranks for in the organic search results for a keyword. |
| `best_position_diff` | `int \| None` | The change in position between your selected dates. |
| `best_position_has_thumbnail` | `bool \| None` | The top position has a thumbnail. |
| `best_position_has_thumbnail_prev` | `bool \| None` | The top position has a thumbnail on the comparison date. |
| `best_position_has_video` | `bool \| None` | The top position has a video. |
| `best_position_has_video_prev` | `bool \| None` | The top position has a video on the comparison date. |
| `best_position_kind` | `BestPositionKindEnum \| None` | The kind of the top position: organic, paid, or a SERP feature. |
| `best_position_kind_merged` | `BestPositionKindEnum` | The kind of the top position optimized for sorting. |
| `best_position_kind_prev` | `BestPositionKindEnum \| None` | The kind of the top position on the comparison date. |
| `best_position_prev` | `int \| None` | The top position on the comparison date. |
| `best_position_set` | `BestPositionSetEnum` | The ranking group of the top position. |
| `best_position_set_prev` | `BestPositionSetEnum \| None` | The ranking group of the top position on the comparison date. |
| `best_position_url` | `str \| None` | The ranking URL in organic search results. |
| `best_position_url_prev` | `str \| None` | The ranking URL on the comparison date. |
| `cpc` | `int \| None` | Cost Per Click shows the average price that advertisers pay for each ad click in paid search results for a keyword, i... |
| `cpc_merged` | `int \| None` | The CPC field optimized for sorting. |
| `cpc_prev` | `int \| None` | The CPC metric on the comparison date. |
| `entities` | `list[dict[str, Any] \| None]` | Organizations, products, persons, works, events, and locations found in a keyword. |
| `is_best_position_set_top_11_50` | `bool` | The ranking group of the top position is 11-50. |
| `is_best_position_set_top_11_50_prev` | `bool \| None` | The ranking group of the top position was 11-50 on the comparison date. |
| `is_best_position_set_top_3` | `bool` | The ranking group of the top position is Top 3. |
| `is_best_position_set_top_3_prev` | `bool \| None` | The ranking group of the top position was Top 3 on the comparison date. |
| `is_best_position_set_top_4_10` | `bool` | The ranking group of the top position is 4-10. |
| `is_best_position_set_top_4_10_prev` | `bool \| None` | The ranking group of the top position was 4-10 on the comparison date. |
| `is_branded` | `bool` | User intent: branded. The user is searching for a specific brand or company name. |
| `is_commercial` | `bool` | User intent: commercial. The user is comparing products or services before making a purchase decision. |
| `is_informational` | `bool` | User intent: informational. The user is looking for information or an answer to a specific question. |
| `is_local` | `bool` | User intent: local. The user is looking for information relevant to a specific location or nearby services. |
| `is_navigational` | `bool` | User intent: navigational. The user is searching for a specific website or web page. |
| `is_transactional` | `bool` | User intent: transactional. The user is ready to complete an action, often a purchase. |
| `keyword` | `str \| None` | The keyword your target ranks for. |
| `keyword_country` | `CountryEnum1` | The country of a keyword your target ranks for. |
| `keyword_difficulty` | `int \| None` | (10 units) An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point ... |
| `keyword_difficulty_merged` | `int \| None` | (10 units) The keyword difficulty field optimized for sorting. |
| `keyword_difficulty_prev` | `int \| None` | (10 units) The keyword difficulty on the comparison date. |
| `keyword_merged` | `str` | The keyword field optimized for sorting. |
| `keyword_prev` | `str \| None` | The keyword your target ranks for on the comparison date. |
| `language` | `str` | The SERP language. |
| `language_prev` | `str \| None` | The SERP language on the comparison date. |
| `last_update` | `str` | The date when we last checked search engine results for a keyword. |
| `last_update_prev` | `str \| None` | The date when we checked search engine results up to the comparison date. |
| `serp_features` | `list[SerpFeaturesItemEnum1 \| None]` | The SERP features that appear in search results for a keyword. |
| `serp_features_count` | `int` | The number of SERP features that appear in search results for a keyword. |
| `serp_features_count_prev` | `int \| None` | The number of SERP features on the comparison date. |
| `serp_features_merged` | `list[SerpFeaturesItemEnum1 \| None]` | The SERP features field optimized for sorting. |
| `serp_features_prev` | `list[SerpFeaturesItemEnum1 \| None]` | The SERP features that appear in search results for a keyword on the comparison date. |
| `serp_target_main_positions_count` | `int` | The number of target URLs ranking for a keyword excluding positions in Sitelinks, Top stories, Image packs, and posts... |
| `serp_target_main_positions_count_prev` | `int \| None` | The number of target URLs ranking for a keyword excluding positions in Sitelinks, Top stories, Image packs, and posts... |
| `serp_target_positions_count` | `int` | The number of target URLs ranking for a keyword. |
| `serp_target_positions_count_prev` | `int \| None` | The number of target URLs ranking for a keyword on the comparison date. |
| `status` | `StatusEnum` | The status of a page: the new page that just started to rank ("left"), the lost page that disappeared from search res... |
| `sum_paid_traffic` | `int \| None` | (10 units) An estimation of the number of monthly visits that your target gets from paid search for a keyword. |
| `sum_paid_traffic_merged` | `int` | (10 units) The paid traffic field optimized for sorting. |
| `sum_paid_traffic_prev` | `int \| None` | (10 units) The paid traffic on the comparison date. |
| `sum_traffic` | `int \| None` | (10 units) An estimation of the number of monthly visitors that your target gets from organic search for a keyword. |
| `sum_traffic_merged` | `int` | (10 units) The traffic field optimized for sorting. |
| `sum_traffic_prev` | `int \| None` | (10 units) The traffic on the comparison date. |
| `volume` | `int \| None` | (10 units) An estimation of the number of searches for a keyword over the latest month. |
| `volume_desktop_pct` | `float \| None` | The percentage of the total search volume that comes from desktop devices. |
| `volume_merged` | `int \| None` | (10 units) The search volume field optimized for sorting. |
| `volume_mobile_pct` | `float \| None` | The percentage of the total search volume that comes from mobile devices. |
| `volume_prev` | `int \| None` | (10 units) The search volume on the comparison date. |
| `words` | `int \| None` | The number of words in a keyword. |
| `words_merged` | `int` | The number of words in a keyword optimized for sorting. |
| `words_prev` | `int \| None` | The number of words in a keyword on the comparison date. |

</details>

### `site_explorer_outlinks_stats()`

Outlinks stats.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |

**Returns:** `SiteExplorerOutlinksStatsData`

| Field | Type | Description |
|-------|------|-------------|
| `outgoing_links` | `int` | The number of external links from the target. |
| `outgoing_links_dofollow` | `int` | The number of external dofollow links from the target. |
| `linked_domains` | `int` | The number of unique root domains linked from the target. |
| `linked_domains_dofollow` | `int` | The number of unique root domains linked via dofollow links from the target. |

### `site_explorer_pages_by_traffic()`

Pages by traffic.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `SiteExplorerPagesByTrafficData`

| Field | Type | Description |
|-------|------|-------------|
| `range0_pages` | `int` | The total number of pages with 0 traffic. |
| `range100_traffic` | `int` | (10 units) The total traffic from pages with 1-100 traffic. |
| `range100_pages` | `int` | The total number of pages with 1-100 traffic. |
| `range1k_traffic` | `int` | (10 units) The total traffic from pages with 101-1K traffic. |
| `range1k_pages` | `int` | The total number of pages with 101-1K traffic. |
| `range5k_traffic` | `int` | (10 units) The total traffic from pages with 1K-5K traffic. |
| `range5k_pages` | `int` | The total number of pages with 1K-5K traffic. |
| `range10k_traffic` | `int` | (10 units) The total traffic from pages with 5K-10K traffic. |
| `range10k_pages` | `int` | The total number of pages with 5K-10K traffic. |
| `range10k_plus_traffic` | `int` | (10 units) The total traffic from pages with 10K+ traffic. |
| `range10k_plus_pages` | `int` | The total number of pages with 10K+ traffic. |

### `site_explorer_pages_history()`

Pages history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerPagesHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `pages` | `int` | The total number of pages from a target ranking in the top 100 organic search results. |

### `site_explorer_paid_pages()`

Paid pages.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **ads_count**: The number of unique ads with a page.   type: integer  **ads_count_diff**: The change in ads between your selected dates.   type: integer  **ads_count_prev**: The number of ads on the comparison date.   type: integer  **cpc**   type: integer nullable  **cpc_prev**: The CPC metric on the comparison date.   type: integer nullable  **description**: The description of an ad as seen in search results.   type: string  **description_prev**: The description of an ad on the comparison date.   type: string  **has_thumbnail**: The position has a thumbnail.   type: boolean  **has_thumbnail_prev**: The position has a thumbnail on the comparison date.   type: boolean  **has_video**: The position has a video.   type: boolean  **has_video_prev**: The position has a video on the comparison date.   type: boolean  **keyword**: The keyword your target ranks for.   type: string  **keyword_difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **keyword_difficulty_prev** (10 units): The keyword difficulty on the comparison date.   type: integer nullable  **keyword_prev**: The keyword your target ranks for on the comparison date.   type: string  **keywords**: The total number of keywords that your target ranks for in paid search results.   type: integer  **keywords_diff**: The change in keywords between your selected dates.   type: integer  **keywords_diff_percent**: The change in keywords between your selected dates, in percents.   type: integer  **keywords_merged**: The total number of keywords optimized for sorting.   type: integer  **keywords_prev**: The keyword your target ranks for on the comparison date.   type: integer  **position**: The position your target ranks for in the paid search results for a keyword.   type: integer  **position_kind**: The kind of a position: organic, paid or a SERP feature. This applies to all positions for a given keyword and URL before picking the top position.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **position_kind_prev**: The kind of a position on the comparison date.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **position_prev**: The position of your target for a given keyword on the comparison date.   type: integer  **raw_url**: The ranking page URL in encoded format.   type: string  **raw_url_prev**: The ranking page URL on the comparison date in encoded format.   type: string  **referring_domains** (5 units): The number of unique domains linking to a page.   type: integer nullable  **serp_features**   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_features_prev**: The SERP features on the comparison date.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **status**: The status of a page: the new page that just started to rank in paid results ("left"), the lost page that disappeared from paid results ("right"), or no change ("both").   type: string   enum: `"left"` `"right"` `"both"`  **sum_traffic** (10 units): An estimation of the monthly paid search traffic that a page gets from all the keywords that it ranks for.   type: integer nullable  **sum_traffic_merged** (10 units): The paid traffic field optimized for sorting.   type: integer  **sum_traffic_prev** (10 units): The paid traffic on the comparison date.   type: integer nullable  **title**: The title of an ad as seen in search results.   type: string  **title_prev**: The title of an ad on the comparison date.   type: string  **top_keyword**: The keyword that brings the most paid traffic to a page.   type: string nullable  **top_keyword_best_position**: The ranking position that a page holds for its top keyword.   type: integer nullable  **top_keyword_best_position_diff**: The change in the top position between your selected dates.   type: integer nullable  **top_keyword_best_position_kind**: The kind of the top position: organic, paid or a SERP feature.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **top_keyword_best_position_kind_prev**: The kind of the top position on the comparison date.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **top_keyword_best_position_prev**: The top position on the comparison date.   type: integer nullable  **top_keyword_best_position_title**: The title displayed for the page in its top keyword's SERP.   type: string nullable  **top_keyword_best_position_title_prev**: The title displayed for the page in its top keyword's SERP on the comparison date.   type: string nullable  **top_keyword_country**: The country in which a page ranks for its top keyword.   type: string nullable   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **top_keyword_country_prev**: The country in which a page ranks for its top keyword on the comparison date.   type: string nullable   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **top_keyword_prev**: The keyword that brings the most paid traffic to a page on the comparison date.   type: string nullable  **top_keyword_volume** (10 units): An estimation of the average monthly number of searches for the top keyword over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable  **top_keyword_volume_prev** (10 units): The search volume on the comparison date.   type: integer nullable  **traffic** (10 units): An estimation of the number of monthly visitors that your target gets from paid search for a keyword.   type: integer  **traffic_diff**: The change in traffic between your selected dates.   type: integer  **traffic_diff_percent**: The change in traffic between your selected dates, in percents.   type: integer  **traffic_prev** (10 units): The traffic from a keyword on the comparison date.   type: integer  **ur**: URL Rating (UR) shows the strength of your target page’s backlink profile on a 100-point logarithmic scale.   type: float nullable  **url**: The ranking page URL.   type: url nullable  **url_prev**: The ranking page URL on the comparison date.   type: url nullable  **url_visual**: The URL of an ad as seen in search results.   type: string  **url_visual_prev**: The URL of an ad on the comparison date.   type: string  **value** (10 units): The estimated cost of a page's monthly paid search traffic, in USD cents.   type: integer nullable  **value_diff**: The change in traffic value between your selected dates.   type: integer  **value_diff_percent**: The change in traffic value between your selected dates, in percents.   type: integer  **value_merged** (10 units): The traffic value field optimized for sorting.   type: integer nullable  **value_prev** (10 units): The traffic value on the comparison date.   type: integer nullable  **volume** (10 units): An estimation of the number of searches for a keyword over the latest month.   type: integer nullable  **volume_prev** (10 units): The search volume on the comparison date.   type: integer nullable  **words**: The number of words in a keyword.   type: integer  **words_prev**: The number of words in a keyword on the comparison date.   type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[SiteExplorerPaidPagesData]`

<details>
<summary>38 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `ads_count` | `int \| None` | The number of unique ads with a page. |
| `ads_count_diff` | `int` | The change in ads between your selected dates. |
| `ads_count_prev` | `int \| None` | The number of ads on the comparison date. |
| `keywords` | `int \| None` | The total number of keywords that your target ranks for in paid search results. |
| `keywords_diff` | `int` | The change in keywords between your selected dates. |
| `keywords_diff_percent` | `int` | The change in keywords between your selected dates, in percents. |
| `keywords_merged` | `int` | The total number of keywords optimized for sorting. |
| `keywords_prev` | `int \| None` | The keyword your target ranks for on the comparison date. |
| `raw_url` | `str` | The ranking page URL in encoded format. |
| `raw_url_prev` | `str \| None` | The ranking page URL on the comparison date in encoded format. |
| `referring_domains` | `int \| None` | (5 units) The number of unique domains linking to a page. |
| `status` | `StatusEnum` | The status of a page: the new page that just started to rank in paid results ("left"), the lost page that disappeared... |
| `sum_traffic` | `int \| None` | (10 units) An estimation of the monthly paid search traffic that a page gets from all the keywords that it ranks for. |
| `sum_traffic_merged` | `int` | (10 units) The paid traffic field optimized for sorting. |
| `sum_traffic_prev` | `int \| None` | (10 units) The paid traffic on the comparison date. |
| `top_keyword` | `str \| None` | The keyword that brings the most paid traffic to a page. |
| `top_keyword_best_position` | `int \| None` | The ranking position that a page holds for its top keyword. |
| `top_keyword_best_position_diff` | `int \| None` | The change in the top position between your selected dates. |
| `top_keyword_best_position_kind` | `BestPositionKindEnum \| None` | The kind of the top position: organic, paid or a SERP feature. |
| `top_keyword_best_position_kind_prev` | `BestPositionKindEnum \| None` | The kind of the top position on the comparison date. |
| `top_keyword_best_position_prev` | `int \| None` | The top position on the comparison date. |
| `top_keyword_best_position_title` | `str \| None` | The title displayed for the page in its top keyword's SERP. |
| `top_keyword_best_position_title_prev` | `str \| None` | The title displayed for the page in its top keyword's SERP on the comparison date. |
| `top_keyword_country` | `CountryEnum1 \| None` | The country in which a page ranks for its top keyword. |
| `top_keyword_country_prev` | `CountryEnum1 \| None` | The country in which a page ranks for its top keyword on the comparison date. |
| `top_keyword_prev` | `str \| None` | The keyword that brings the most paid traffic to a page on the comparison date. |
| `top_keyword_volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for the top keyword over the latest month or over ... |
| `top_keyword_volume_prev` | `int \| None` | (10 units) The search volume on the comparison date. |
| `traffic_diff` | `int` | The change in traffic between your selected dates. |
| `traffic_diff_percent` | `int` | The change in traffic between your selected dates, in percents. |
| `ur` | `float \| None` | URL Rating (UR) shows the strength of your target page’s backlink profile on a 100-point logarithmic scale. |
| `url` | `str \| None` | The ranking page URL. |
| `url_prev` | `str \| None` | The ranking page URL on the comparison date. |
| `value` | `int \| None` | (10 units) The estimated cost of a page's monthly paid search traffic, in USD cents. |
| `value_diff` | `int` | The change in traffic value between your selected dates. |
| `value_diff_percent` | `int` | The change in traffic value between your selected dates, in percents. |
| `value_merged` | `int \| None` | (10 units) The traffic value field optimized for sorting. |
| `value_prev` | `int \| None` | (10 units) The traffic value on the comparison date. |

</details>

### `site_explorer_refdomains()`

Refdomains.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **anchor**: The clickable words in a link that point to a URL.   type: string  **discovered_status**: The reason the link was discovered during the last crawl: the page was crawled for the first time, the link was added to the page, or the link re-appeared after being removed.   type: string nullable   enum: `"pagefound"` `"linkfound"` `"linkrestored"`  **dofollow_linked_domains**: The number of unique root domains with dofollow links linked from the referring domain.   type: integer  **dofollow_links**: The number of links from the referring domain to your target that don't have the “nofollow” attribute.   type: integer  **dofollow_refdomains** (5 units): The number of unique domains with dofollow links to the referring domain.   type: integer  **domain**: A referring domain that has at least one link to your target.   type: string  **domain_rating**: The strength of a domain's backlink profile compared to the others in our database on a 100-point scale.   type: float  **drop_reason**: The reason we removed the link from our index.   type: string nullable   enum: `"manual"` `"noratingunused"` `"notop"` `"tooold"` `"oldunavailable"` `"rescursive"` `"duplicate"` `"nxdomain"` `"malformed"` `"blockedport"` `"disallowed"` `"unlinked"`  **first_seen**: The date we first found a backlink to your target from the referring domain.   type: datetime  **ip_source**: The referring domain IP address.   type: string nullable  **is_content**: The link was found in the biggest piece of content on the page.   type: boolean  **is_dofollow**: The link has no special nofollow attribute.   type: boolean  **is_homepage_link**: The link was found on the homepage of a referring website.   type: boolean  **is_nofollow**: The link or the referring page has the nofollow attribute set.   type: boolean  **is_non_html**: The link points to a URL with non-HTML content.   type: boolean  **is_root_domain**: The domain name is a root domain name.   type: boolean  **is_spam**: Indicates whether the backlink comes from a known spammy domain.   type: boolean  **is_sponsored**: The link has the Sponsored attribute set in the referring page HTML.   type: boolean  **is_ugc**: The link has the User Generated Content attribute set in the referring page HTML.   type: boolean  **languages**: The languages listed in the referring page metadata or detected by the crawler to appear in the HTML.   type: array(string)  **last_seen**: The date your target lost its last live backlink for the referring domain.   type: datetime nullable  **len_url_redirect**: The number of redirect chain URLs.   type: integer  **link_type**: The kind of the backlink.   type: string   enum: `"redirect"` `"frame"` `"text"` `"form"` `"canonical"` `"alternate"` `"rss"` `"image"`  **linked_domains**: The number of unique root domains linked from the referring page.   type: integer  **links_external**: The number of external links from the referring page.   type: integer  **links_to_target**: The number of backlinks from the referring domain to your target.   type: integer  **lost_links**: The number of backlinks lost from the referring domain for the selected time period.   type: integer  **lost_reason**: The reason the link was lost during the last crawl.   type: string nullable   enum: `"removedfromhtml"` `"notcanonical"` `"noindex"` `"pageredirected"` `"pageerror"` `"lostredirect"` `"notfound"`  **new_links**: The number of new backlinks found from the referring domain for the selected time period.   type: integer  **noindex**: The referring page has the noindex meta attribute.   type: boolean  **port_source**: The network port of the referring page URL.   type: integer  **port_target**: The network port of the target page URL.   type: integer  **positions**: The number of keywords that the referring page ranks for in the top 100 positions.   type: integer  **positions_source_domain**: The number of keywords that the referring domain ranks for in the top 100 positions.   type: integer  **powered_by**: Web technologies used to build and serve the referring page content.   type: array(string)  **refdomains** (5 units): The number of unique referring domains linking to the referring page.   type: integer  **root_domain_name**: The root domain name of the referring domain, not including subdomains.   type: string  **snippet_left**: The snippet of text appearing just before the link.   type: string  **snippet_right**: The snippet of text appearing just after the link.   type: string  **source_page_author**: The author of the referring page.   type: string nullable  **title**: The html title of the referring page.   type: string  **traffic_domain** (10 units): The referring domain's estimated monthly organic traffic from search.   type: integer  **traffic_page** (10 units): The referring page's estimated monthly organic traffic from search.   type: integer  **url_from**: The URL of the page containing a link to your target.   type: string  **url_redirect**: A redirect chain the target URL of the link points to.   type: array(url)  **url_redirect_with_target**: The target URL of the link with its redirect chain.   type: array(string)  **url_to**: The URL the backlink points to.   type: string |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `history` | `str` | No | A time frame to add lost backlinks to the report. Choose between `live` (no history), `since:<date>` (history since a specified date), and `all_time` (full history). The date should be in YYYY-MM-DD format. |

**Returns:** `list[SiteExplorerRefdomainsData]`

| Field | Type | Description |
|-------|------|-------------|
| `dofollow_linked_domains` | `int` | The number of unique root domains with dofollow links linked from the referring domain. |
| `dofollow_links` | `int` | The number of links from the referring domain to your target that don't have the “nofollow” attribute. |
| `dofollow_refdomains` | `int` | (5 units) The number of unique domains with dofollow links to the referring domain. |
| `domain` | `str` | A referring domain that has at least one link to your target. |
| `domain_rating` | `float` | The strength of a domain's backlink profile compared to the others in our database on a 100-point scale. |
| `first_seen` | `str` | The date we first found a backlink to your target from the referring domain. |
| `ip_source` | `str \| None` | The referring domain IP address. |
| `is_root_domain` | `bool` | The domain name is a root domain name. |
| `is_spam` | `bool` | Indicates whether the backlink comes from a known spammy domain. |
| `last_seen` | `str \| None` | The date your target lost its last live backlink for the referring domain. |
| `links_to_target` | `int` | The number of backlinks from the referring domain to your target. |
| `lost_links` | `int` | The number of backlinks lost from the referring domain for the selected time period. |
| `new_links` | `int` | The number of new backlinks found from the referring domain for the selected time period. |
| `positions_source_domain` | `int` | The number of keywords that the referring domain ranks for in the top 100 positions. |
| `traffic_domain` | `int` | (10 units) The referring domain's estimated monthly organic traffic from search. |

### `site_explorer_refdomains_history()`

Refdomains history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerRefdomainsHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `refdomains` | `int` | (5 units) The total number of unique domains linking to your target. |

### `site_explorer_top_pages()`

Top pages.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `timeout` | `int` | No | A manual timeout duration in seconds. |
| `limit` | `int` | No | The number of results to return. |
| `order_by` | `str` | No | A column to order results by. See response schema for valid column identifiers. |
| `where` | `str` | No | The filter expression. The following column identifiers are recognized (this differs from the identifiers recognized by the `select` parameter).  **cpc**   type: integer nullable  **cpc_prev**: The CPC metric on the comparison date.   type: integer nullable  **has_thumbnail**: The position has a thumbnail.   type: boolean  **has_thumbnail_prev**: The position has a thumbnail on the comparison date.   type: boolean  **has_video**: The position has a video.   type: boolean  **has_video_prev**: The position has a video on the comparison date.   type: boolean  **keyword**: The keyword your target ranks for.   type: string  **keyword_difficulty** (10 units): An estimation of how hard it is to rank in the top 10 organic search results for a keyword on a 100-point scale.   type: integer nullable  **keyword_difficulty_prev** (10 units): The keyword difficulty on the comparison date.   type: integer nullable  **keyword_prev**: The keyword your target ranks for on the comparison date.   type: string  **keywords**: The total number of keywords that your target ranks for in the top 100 organic search results.   type: integer  **keywords_diff**: The change in keywords between your selected dates.   type: integer  **keywords_diff_percent**: The change in keywords between your selected dates, in percents.   type: integer  **keywords_merged**: The total number of keywords optimized for sorting.   type: integer  **keywords_prev**: The keyword your target ranks for on the comparison date.   type: integer  **position**: The position your target ranks for in the organic search results for a keyword.   type: integer  **position_kind**: The kind of a position: organic, paid or a SERP feature. This applies to all positions for a given keyword and URL before picking the top position.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **position_kind_prev**: The kind of a position on the comparison date.   type: string   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **position_prev**: The position of your target for a given keyword on the comparison date.   type: integer  **raw_url**: The ranking page URL in encoded format.   type: string  **raw_url_prev**: The ranking page URL on the comparison date in encoded format.   type: string  **referring_domains** (5 units): The number of unique domains linking to a page.   type: integer nullable  **serp_features**   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **serp_features_prev**: The SERP features on the comparison date.   type: array(string)   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"` `"image_th"` `"video_th"` `"ai_overview_found"`  **status**: The status of a page: the new page that just started to rank ("left"), the lost page that disappeared from search results ("right"), or no change ("both").   type: string   enum: `"left"` `"right"` `"both"`  **sum_traffic** (10 units): An estimation of the monthly organic search traffic that a page gets from all the keywords that it ranks for.   type: integer nullable  **sum_traffic_merged** (10 units): The traffic field optimized for sorting.   type: integer  **sum_traffic_prev** (10 units): The traffic on the comparison date.   type: integer nullable  **top_keyword**: The keyword that brings the most organic traffic to a page.   type: string nullable  **top_keyword_best_position**: The ranking position that a page holds for its top keyword.   type: integer nullable  **top_keyword_best_position_diff**: The change in the top position between your selected dates.   type: integer nullable  **top_keyword_best_position_kind**: The kind of the top position: organic, paid or a SERP feature.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **top_keyword_best_position_kind_prev**: The kind of the top position on the comparison date.   type: string nullable   enum: `"paid_top"` `"paid_bottom"` `"paid_right"` `"paid_sitelink"` `"organic"` `"sitelink"` `"snippet"` `"image"` `"article"` `"knowledge_card"` `"knowledge_panel"` `"local_pack"` `"local_teaser"` `"news"` `"question"` `"review"` `"shopping"` `"tweet"` `"spelling"` `"video"` `"discussion"` `"ai_overview"` `"ai_overview_sitelink"` `"organic_shopping"`  **top_keyword_best_position_prev**: The top position on the comparison date.   type: integer nullable  **top_keyword_best_position_title**: The title displayed for the page in its top keyword's SERP.   type: string nullable  **top_keyword_best_position_title_prev**: The title displayed for the page in its top keyword's SERP on the comparison date.   type: string nullable  **top_keyword_country**: The country in which a page ranks for its top keyword.   type: string nullable   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **top_keyword_country_prev**: The country in which a page ranks for its top keyword on the comparison date.   type: string nullable   enum: `"AD"` `"AE"` `"AF"` `"AG"` `"AI"` `"AL"` `"AM"` `"AO"` `"AQ"` `"AR"` `"AS"` `"AT"` `"AU"` `"AW"` `"AX"` `"AZ"` `"BA"` `"BB"` `"BD"` `"BE"` `"BF"` `"BG"` `"BH"` `"BI"` `"BJ"` `"BL"` `"BM"` `"BN"` `"BO"` `"BQ"` `"BR"` `"BS"` `"BT"` `"BV"` `"BW"` `"BY"` `"BZ"` `"CA"` `"CC"` `"CD"` `"CF"` `"CG"` `"CH"` `"CI"` `"CK"` `"CL"` `"CM"` `"CN"` `"CO"` `"CR"` `"CU"` `"CV"` `"CW"` `"CX"` `"CY"` `"CZ"` `"DE"` `"DJ"` `"DK"` `"DM"` `"DO"` `"DZ"` `"EC"` `"EE"` `"EG"` `"EH"` `"ER"` `"ES"` `"ET"` `"FI"` `"FJ"` `"FK"` `"FM"` `"FO"` `"FR"` `"GA"` `"GB"` `"GD"` `"GE"` `"GF"` `"GG"` `"GH"` `"GI"` `"GL"` `"GM"` `"GN"` `"GP"` `"GQ"` `"GR"` `"GS"` `"GT"` `"GU"` `"GW"` `"GY"` `"HK"` `"HM"` `"HN"` `"HR"` `"HT"` `"HU"` `"ID"` `"IE"` `"IL"` `"IM"` `"IN"` `"IO"` `"IQ"` `"IR"` `"IS"` `"IT"` `"JE"` `"JM"` `"JO"` `"JP"` `"KE"` `"KG"` `"KH"` `"KI"` `"KM"` `"KN"` `"KP"` `"KR"` `"KW"` `"KY"` `"KZ"` `"LA"` `"LB"` `"LC"` `"LI"` `"LK"` `"LR"` `"LS"` `"LT"` `"LU"` `"LV"` `"LY"` `"MA"` `"MC"` `"MD"` `"ME"` `"MF"` `"MG"` `"MH"` `"MK"` `"ML"` `"MM"` `"MN"` `"MO"` `"MP"` `"MQ"` `"MR"` `"MS"` `"MT"` `"MU"` `"MV"` `"MW"` `"MX"` `"MY"` `"MZ"` `"NA"` `"NC"` `"NE"` `"NF"` `"NG"` `"NI"` `"NL"` `"NO"` `"NP"` `"NR"` `"NU"` `"NZ"` `"OM"` `"OTHER"` `"PA"` `"PE"` `"PF"` `"PG"` `"PH"` `"PK"` `"PL"` `"PM"` `"PN"` `"PR"` `"PS"` `"PT"` `"PW"` `"PY"` `"QA"` `"RE"` `"RO"` `"RS"` `"RU"` `"RW"` `"SA"` `"SB"` `"SC"` `"SD"` `"SE"` `"SG"` `"SH"` `"SI"` `"SJ"` `"SK"` `"SL"` `"SM"` `"SN"` `"SO"` `"SR"` `"SS"` `"ST"` `"SV"` `"SX"` `"SY"` `"SZ"` `"TC"` `"TD"` `"TF"` `"TG"` `"TH"` `"TJ"` `"TK"` `"TL"` `"TM"` `"TN"` `"TO"` `"TR"` `"TT"` `"TV"` `"TW"` `"TZ"` `"UA"` `"UG"` `"UM"` `"US"` `"UY"` `"UZ"` `"VA"` `"VC"` `"VE"` `"VG"` `"VI"` `"VN"` `"VU"` `"WF"` `"WS"` `"YE"` `"YT"` `"ZA"` `"ZM"` `"ZW"`  **top_keyword_prev**: The keyword that brings the most organic traffic to a page on the comparison date.   type: string nullable  **top_keyword_volume** (10 units): An estimation of the average monthly number of searches for the top keyword over the latest month or over the latest known 12 months of data depending on the "volume_mode" parameter.   type: integer nullable  **top_keyword_volume_prev** (10 units): The search volume on the comparison date.   type: integer nullable  **traffic** (10 units): An estimation of the number of monthly visitors that your target gets from organic search for a keyword.   type: integer  **traffic_diff**: The change in traffic between your selected dates.   type: integer  **traffic_diff_percent**: The change in traffic between your selected dates, in percents.   type: integer  **traffic_prev** (10 units): The traffic from a keyword on the comparison date.   type: integer  **ur**: URL Rating (UR) shows the strength of your target page’s backlink profile on a 100-point logarithmic scale.   type: float nullable  **url**: The ranking page URL.   type: url nullable  **url_prev**: The ranking page URL on the comparison date.   type: url nullable  **value** (10 units): The estimated value of a page's monthly organic search traffic, in USD cents.   type: integer nullable  **value_diff**: The change in traffic value between your selected dates.   type: integer  **value_diff_percent**: The change in traffic value between your selected dates, in percents.   type: integer  **value_merged** (10 units): The traffic value field optimized for sorting.   type: integer nullable  **value_prev** (10 units): The traffic value on the comparison date.   type: integer nullable  **volume** (10 units): An estimation of the number of searches for a keyword over the latest month.   type: integer nullable  **volume_prev** (10 units): The search volume on the comparison date.   type: integer nullable  **words**: The number of words in a keyword.   type: integer  **words_prev**: The number of words in a keyword on the comparison date.   type: integer |
| `select` | `SelectStr` | Yes | A comma-separated list of columns to return. See response schema for valid column identifiers. |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `date_compared` | `DateStr` | No | A date to compare metrics with in YYYY-MM-DD format. |
| `date` | `DateStr` | Yes | A date to report metrics on in YYYY-MM-DD format. |
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |

**Returns:** `list[SiteExplorerTopPagesData]`

<details>
<summary>35 fields</summary>

| Field | Type | Description |
|-------|------|-------------|
| `keywords` | `int \| None` | The total number of keywords that your target ranks for in the top 100 organic search results. |
| `keywords_diff` | `int` | The change in keywords between your selected dates. |
| `keywords_diff_percent` | `int` | The change in keywords between your selected dates, in percents. |
| `keywords_merged` | `int` | The total number of keywords optimized for sorting. |
| `keywords_prev` | `int \| None` | The keyword your target ranks for on the comparison date. |
| `raw_url` | `str` | The ranking page URL in encoded format. |
| `raw_url_prev` | `str \| None` | The ranking page URL on the comparison date in encoded format. |
| `referring_domains` | `int \| None` | (5 units) The number of unique domains linking to a page. |
| `status` | `StatusEnum` | The status of a page: the new page that just started to rank ("left"), the lost page that disappeared from search res... |
| `sum_traffic` | `int \| None` | (10 units) An estimation of the monthly organic search traffic that a page gets from all the keywords that it ranks for. |
| `sum_traffic_merged` | `int` | (10 units) The traffic field optimized for sorting. |
| `sum_traffic_prev` | `int \| None` | (10 units) The traffic on the comparison date. |
| `top_keyword` | `str \| None` | The keyword that brings the most organic traffic to a page. |
| `top_keyword_best_position` | `int \| None` | The ranking position that a page holds for its top keyword. |
| `top_keyword_best_position_diff` | `int \| None` | The change in the top position between your selected dates. |
| `top_keyword_best_position_kind` | `BestPositionKindEnum \| None` | The kind of the top position: organic, paid or a SERP feature. |
| `top_keyword_best_position_kind_prev` | `BestPositionKindEnum \| None` | The kind of the top position on the comparison date. |
| `top_keyword_best_position_prev` | `int \| None` | The top position on the comparison date. |
| `top_keyword_best_position_title` | `str \| None` | The title displayed for the page in its top keyword's SERP. |
| `top_keyword_best_position_title_prev` | `str \| None` | The title displayed for the page in its top keyword's SERP on the comparison date. |
| `top_keyword_country` | `CountryEnum1 \| None` | The country in which a page ranks for its top keyword. |
| `top_keyword_country_prev` | `CountryEnum1 \| None` | The country in which a page ranks for its top keyword on the comparison date. |
| `top_keyword_prev` | `str \| None` | The keyword that brings the most organic traffic to a page on the comparison date. |
| `top_keyword_volume` | `int \| None` | (10 units) An estimation of the average monthly number of searches for the top keyword over the latest month or over ... |
| `top_keyword_volume_prev` | `int \| None` | (10 units) The search volume on the comparison date. |
| `traffic_diff` | `int` | The change in traffic between your selected dates. |
| `traffic_diff_percent` | `int` | The change in traffic between your selected dates, in percents. |
| `ur` | `float \| None` | URL Rating (UR) shows the strength of your target page’s backlink profile on a 100-point logarithmic scale. |
| `url` | `str \| None` | The ranking page URL. |
| `url_prev` | `str \| None` | The ranking page URL on the comparison date. |
| `value` | `int \| None` | (10 units) The estimated value of a page's monthly organic search traffic, in USD cents. |
| `value_diff` | `int` | The change in traffic value between your selected dates. |
| `value_diff_percent` | `int` | The change in traffic value between your selected dates, in percents. |
| `value_merged` | `int \| None` | (10 units) The traffic value field optimized for sorting. |
| `value_prev` | `int \| None` | (10 units) The traffic value on the comparison date. |

</details>

### `site_explorer_total_search_volume_history()`

Total search volume history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `volume_mode` | `VolumeModeEnum` | No | The search volume calculation mode: monthly or average. It affects volume, traffic, and traffic value. |
| `top_positions` | `ViewForEnum` | No | The number of top organic search positions to consider when calculating total search volume. |
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `country` | `CountryEnum` | No | A two-letter country code (ISO 3166-1 alpha-2). |
| `protocol` | `ProtocolEnum` | No | The protocol of your target. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |
| `mode` | `ModeEnum` | No | The scope of the search based on the target you entered. |

**Returns:** `list[SiteExplorerTotalSearchVolumeHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `total_search_volume` | `int` | (10 units) The total search volume of keywords for which your target ranks within the specified `top_positions` in th... |

### `site_explorer_url_rating_history()`

URL Rating history.

**Parameters:**

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `history_grouping` | `HistoryGroupingEnum` | No | The time interval used to group historical data. |
| `date_to` | `DateStr` | No | The end date of the historical period in YYYY-MM-DD format. |
| `date_from` | `DateStr` | Yes | The start date of the historical period in YYYY-MM-DD format. |
| `target` | `str` | Yes | The target of the search: a domain or a URL. |

**Returns:** `list[SiteExplorerUrlRatingHistoryData]`

| Field | Type | Description |
|-------|------|-------------|
| `date` | `str` |  |
| `url_rating` | `float` | The strength of your target page's backlink profile compared to the other websites in our database on a 100-point log... |

