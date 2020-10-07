# A1 DATA CURATION

## Objective
Construct, analyze, and publish a dataset of monthly traffic on English Wikipedia from January 1 2008 through August 30 2020. 
Data is obtained from two different Wikimedia [REST API](https://www.mediawiki.org/wiki/Wikimedia_REST_API) endpoints which are combined into a single dataset.

### API Documentation Reference

The Legacy Pagecounts API ([documentation] (https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end), [endpoint] (https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)) provides access to desktop and mobile traffic data from January 2008 through July 2016.
The Pageviews API ([documentation] (https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end), [endpoint] (https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through August 2020.

## Final CSV Fields

The final csv file contains the following columns:

| Column                      | Value             |
|-----------------------------|-------------------|
| year                        | YYYY              |
| month                       | MM                |
| pagecount_all_views         | num_views         | 
| pagecount_desktop_views     | num_views         |
| pagecount_mobile_views      | num_views         |
| pageview_all_views          | num_views         |
| pageview_desktop_views      | num_views         |
| pageview_mobile_views       | num_views         |

## Terms of Use
The source data and wikimedia terms of use are linked [here](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions).
The jupyter notebook is available under the [MIT License](LICENSE)

## Notes
As much as possible, we're interested in organic (user) traffic, as opposed to traffic by web crawlers or spiders. The Pageview API (but not the Pagecount API) allows you to filter by agent=user and is done in the notebook.

There was about 1 year of overlapping traffic data between the two APIs. Overlap can be observed in the final plot.
