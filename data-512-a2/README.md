# A2 DATA INTERROGATION - BIAS IN DATA

## Objective
Identify potential sources of bias in a corpus of human-annotated data, and describe some implications of those biases. The Wikipedia Talk corpus is used and it consists of three datasets. Each dataset contains thousands of online discussion posts made by Wikipedia editors who were discussing how to write and edit Wikipedia articles. Crowdworkers labelled these posts for three kinds of hostile speech: “toxicity”, “aggression”, and “personal attacks”. The current analysis focuses on the "toxicity" and "personal attacks" dataset.

Analyses are performed to identify if there is a suitable representations of population groups in the labellers sample, if certain demographics are unfairly marginalized due to the labelling, and exploration of time trends of word usage. Initial investigation reveals some of the most common 'toxic' labels as follows: 

![Alt text](images/toxic_wc.png?raw=true "Top words flagged as toxic")


## API Documentation Reference

The Legacy Pagecounts API ([documentation](https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end), [endpoint](https://wikitech.wikimedia.org/wiki/Analytics/AQS/Legacy_Pagecounts)) provides access to desktop and mobile traffic data from January 2008 through July 2016.

The Pageviews API ([documentation](https://wikimedia.org/api/rest_v1/#/Pagecounts_data_(legacy)/get_metrics_legacy_pagecounts_aggregate_project_access_site_granularity_start_end), [endpoint](https://wikimedia.org/api/rest_v1/#/Pageviews_data/get_metrics_pageviews_aggregate_project_access_agent_granularity_start_end)) provides access to desktop, mobile web, and mobile app traffic data from July 2015 through August 2020.

** Usage of the data must honor the [Terms of Use](https://foundation.wikimedia.org/wiki/Terms_of_Use/en) and Wikimedia's [Privacy Policy](https://foundation.wikimedia.org/wiki/Privacy_policy)

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
The source data and wikimedia terms of use are available through the [Wikimedia Foundation](https://www.mediawiki.org/wiki/Wikimedia_REST_API#Terms_and_conditions).
The project is available under the [MIT License](LICENSE)

## Notes
As much as possible, we're interested in organic (user) traffic, as opposed to traffic by web crawlers or spiders. The Pageview API (but not the Pagecount API) allows you to filter by agent=user and is done in the notebook.

There was about 1 year of overlapping traffic data between the two APIs. Overlap can be observed in the final plot.
