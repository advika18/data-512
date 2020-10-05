# A1 DATA CURATION

## Objective
Construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through August 30 2020. 
Data is obtained from two different Wikimedia [REST API](https://www.mediawiki.org/wiki/Wikimedia_REST_API) endpoints which is combined into a single dataset.

## Terms of Use
The source data and wikimedia terms of use are linked [here](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions).
The jupyter notebook is available under the [MIT License](LICENSE)

### API Documentation Reference
[REST API]()https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end)
[Pagecount endpoint](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)
[Pageviews endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)

## Final CSV Fields

The final csv file contains the following columns:
| Columns                     |
| year                        | 
| month                       | 
| pagecount_all_views         | 
| pagecount_desktop_views     | 
| pagecount_mobile_views      | 
| pageview_all_views          | 
| pageview_desktop_views      | 
| pageview_mobile_views       | 


## Notes
As much as possible, we're interested in organic (user) traffic, as opposed to traffic by web crawlers or spiders. The Pageview API (but not the Pagecount API) allows you to filter by agent=user and is done in the notebook.

There was about 1 year of overlapping traffic data between the two APIs. Overlap can be observed in the final plot.
