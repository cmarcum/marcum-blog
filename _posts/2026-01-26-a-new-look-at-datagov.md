---
layout: post
title: "There's a New Look at Data.gov."
date: 2026-01-24
tags: [federal-data,open-data]
---

The [Data.gov](data.gov) team rolled out a beta-version of the next iteration of the Federal Data Catalog: [https://catalog-beta.data.gov/](https://catalog-beta.data.gov/).  While there does not appear to be a new landing page as part of this release, there are notable changes to the look and feel of the catalog search page as well as to individual dataset pages (compare with [https://catalog.data.gov](https://catalog.data.gov)).  The beta-version is much more barebones. The current catalog.data.gov utilizes a traditional, density-focused layout characterized by a sidebar-heavy navigation system and a wide variety of explicit filters and sorting options visible immediately on the search page. In contrast, the beta-version adopts a more modern, streamlined aesthetic with a centralized search focus. It's unclear whether the limited sorting options will be expanded upon in the future - the current options in the beta-version sorting by "Relevance" and "Popularity". The filters have been moved to the right of the search form and dataset cards, and the geography filter has been moved to the bottom of the stack. The dataset cards are both more descrptive and less busy; they now include information about last-updated dates, search relevance, and view metrics. While the original site is information-dense, typical of older CKAN (Comprehensive Knowledge Archive Network) implementations, the beta-version appears to be prioritizing a "mobile-first" feel.

<img width="767" height="363" alt="image" src="https://github.com/user-attachments/assets/b367ab46-a83a-49de-93d3-5f1e317db277" />

One of the most notable changes is to the count of datasets appearing below the search bar. There is a large discrepancy between the active catalog, which, as of today, lists 391,139 datasets in the FDC while the beta-version lists 511,462. What's going on here? Well, Tim Lowden (head of the Data.gov team) [clarified on my linked-in post about this ](https://www.linkedin.com/feed/update/urn:li:ugcPost:7420899797458546688?commentUrn=urn%3Ali%3Acomment%3A%28ugcPost%3A7420899797458546688%2C7420937858120593410%29&dashCommentUrn=urn%3Ali%3Afsd_comment%3A%287420937858120593410%2Curn%3Ali%3AugcPost%3A7420899797458546688%29) that the variance results from the beta-version resolving a long-standing issue with how Data.gov indexed "collections" of datasets. According to the [User Guide](https://data.gov/user-guide/#dataset-totals), the current live page total was based on counting collections of datasets as a single data asset and ignored the number of assets within each collection. So, the live page total reflects a significant undercount of the actual datasets indexed in the Federal Data Catalog. 

This was one of the issues that Hyon Kim (who used to lead the Data.gov team at GSA) and I spoke about during our Data Foundation Webinar last fall: [Beyond the Headlines: What's Really Happened in 2025 to data.gov, Open Data, and Data Leadership] (https://datafoundation.org/news/past-events/704/704-Beyond-the-Headlines-Whats-Really-Happened-in-2025-to-datagov-Open-Data-and-Data-Leadership). Basically, the dataset count could change not because underlying data assets were added or removed, but because they were added to or removed from a data collection instead (meaning the total true number could remain the same in that case). 

I could take or leave the initial changes to the aesthetics Federal Data Catalog as reflected in the beta-version. However, the improving the accuracy of its accounting is a welcome update.

To see where the figures come from, you can evaluate the CKAN API directly. The dynamic count value returns the current number of datasets indexed in the Federal Data Catalog (counting collections as single units):

```
https://catalog.data.gov/api/3/action/package_search?&rows=0
```
which currently returns:
```
{
  "help": "https://catalog.data.gov/api/3/action/help_show?name=package_search",
  "success": true,
  "result": {
    "count": 391139,
    "facets": {

    },
    "results": [],
    "sort": "views_recent desc",
    "search_facets": {

    }
  }
}
```
Likewise, the dynamic count of the total number of datasets that are a part of collections can be called up like this:
```
https://catalog.data.gov/api/3/action/package_search?fq=collection_package_id:*&rows=0
```
which currently returns:
```
{
  "help": "https://catalog.data.gov/api/3/action/help_show?name=package_search",
  "success": true,
  "result": {
    "count": 113495,
    "facets": {

    },
    "results": [],
    "sort": "views_recent desc",
    "search_facets": {

    }
  }
}
```
The sums of those two counts should be pretty close to the new total reported on the beta-version of the site, and it is: 391,139+113,495=504,634. The difference is within normal and can be accounted for by variations in the static number the websites use versus the more up-to-date count from the API.
