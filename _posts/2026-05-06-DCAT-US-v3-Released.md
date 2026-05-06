---
layout: post
title: "DCAT-US 3.0 has been Released for Federal Data"
date: 2026-05-06
tags: [open science, open data, government data]
---

<img width="1536" height="1024" alt="Image generated using the Microsoft Copilot Image Generation Model with the prompt: I want a stylized conceptional graphic advertising DCAT-US 3.0" src="https://github.com/user-attachments/assets/783ce0f4-06ac-4b5b-a262-14cc8c703540" />

<img width="826" height="261" alt="screenshot of dcat-us 3.0 overview" src="https://github.com/user-attachments/assets/63f2d28c-b818-47e4-8508-91aacbe99696" />

One of the most significant accomplishments I had the privilege of co-leading at the Office of Management and Budget (OMB) was the promulgation of [M-25-05](https://whitehouse.gov/wp-content/uploads/2025/01/M-25-05-Phase-2-Implementation-of-the-Foundations-for-Evidence-Based-Policymaking-Act-of-2018-Open-Government-Data-Access-and-Management-Guidance.pdf), OMB's implementation guidance for the Open Government Data Act.  For several years during the development of the guidance, I also co-chaired the [FAIRness project](https://web.archive.org/web/20260115112258/https://www.cdo.gov/fairness-project/), a collaboration between the Chief Data Officers Council and the Interagency Council on Statistical Policy to update the government's standardized metadata schema for use in agencies' comprehensive data inventories and the [Federal Data Catalog](https://catalog.data.gov), which is provided by Data.gov. The two efforts were complementary and M-25-05 set the expectation that the results of the FAIRness project - a new metadata standard called DCAT-US 3.0 - would be adopted by all federal agencies and the General Services Administration (GSA), which hosts Data.gov. 

Finally, after much delay, GSA has released [DCAT US v3.0](https://resources.data.gov/resources/dcat-us3/).

The release of [DCAT US v3.0](https://resources.data.gov/resources/dcat-us3/) provides an modernized approach to describing datasets, APIs, and related resources across federal agencies. The revision is a profile of the widely recognized [W3C DCAT 3](https://www.w3.org/TR/vocab-dcat-3/) specification and introduces a more structured metadata model that supports long-term findability, accessibility, interoperability, reuseability [(FAIRness)](https://www.go-fair.org/fair-principles/). Agencies have worked with DCAT US v1.1 for many years, and the new version reflects accumulated experience as well as the growing need for consistent metadata across diverse data types and delivery mechanisms. The new standard also improves the AI-readiness of federal data. 

## What's Changed?
One of the most visible changes is the introduction of `DataService` as a catalog entity. Agencies increasingly publish their data through use use of enterprise cataloging software that are accessed through an application programming interface (API). Previously, agencies would embed the API information inside distributions or add the API baseurl and call to a specific dataset into a URL metadata field or other free text field, which created inconsistencies and limited discoverability. `DataService` provides a clearer way to describe endpoints, authentication patterns, and service characteristics for access to data and metadata on the agency sites. The update also introduces `DatasetSeries`, which gives agencies a formal way to represent recurring or versioned releases. This is useful for statistical programs, environmental monitoring, and other domains where data is produced on a regular schedule.

The new version also replaces several free text fields with structured objects. Importantly, geospatial (or spatial) and temporal data now have coverage and use defined classes that support machine readability. Previously, geospatial data were handled on an ad-hoc basis by pointing to external profiles in free-text elements (i.e., describing GeoJSON or another format). DCAT-US 3.0 natively supports geospatial data. Restrictions on access and use are represented through explicit objects rather than narrative descriptions. These changes reduce ambiguity and support more reliable validation and discovery. They also help agencies meet expectations (and the law) for transparency and consistency in how they describe the conditions under which data can be accessed or reused. 

DCAT US v3.0 introduces requirement levels for every field. Each element is labeled as mandatory, recommended, or optional. This helps agencies prioritize migration work and understand which elements are essential for compliance. The schema includes updated definitions for identifiers, agents, and quality measurements, which brings the federal profile closer to international practice.

Here's a brief summary of the changes. I strongly recommend reading the very nicely written detailed description of the revision on [resources.data.gov](https://resources.data.gov/resources/dcat-us3/), as well as reviewing the GSA's [GitHub repository for the standard](https://github.com/GSA/dcat-us).

Table of Selected Changes from v1.1 to v3.0
| Element | v1.1 Behavior | v3.0 Behavior |
|--------|----------------|----------------|
| `modified` | Allowed intervals or ambiguous formats | Must be a single ISO 8601 date |
| `temporal` | Free text | Structured `PeriodOfTime` object |
| `spatial` | Free text | Structured `Location` object with WKT, GML, or GeoJSON |
| `language` | Free text names | BCP 47 language tags |
| `accrualPeriodicity` | Free text | Controlled vocabulary or concept object |
| API metadata | Embedded in distributions | Represented using `DataService` |
| Recurring releases | No formal structure | Represented using `DatasetSeries` |
| Access and use restrictions | Free text | Structured restriction classes |

## An outgrowth of the FAIRness Project
These changes collectively support greater FAIRness. The structured approach improves findability by making key metadata elements more consistent. Interoperability improves through alignment with global standards. Reusability benefits from clearer descriptions of provenance, restrictions, and relationships among datasets. Accessibility is strengthened through more predictable metadata patterns that can be interpreted by both humans and automated systems.

As I mentioned above, the update also supports AI readiness. Modern AI systems rely on well structured metadata to locate, interpret, and integrate data from multiple sources. The shift toward explicit objects for spatial, temporal, and access information reduces the need for custom parsing or heuristic interpretation. The addition of `DataService` helps automated systems understand how to interact with APIs. The clearer representation of dataset relationships supports more accurate linking and inference. With the Administration prioritizing data for use in AI applications, such as with the Department of Energy's Genesis Mission, [of which I describe the need for DCAT-US 3.0 at a recent Data Foundation Webinar](https://datafoundation.org/news/past-events/847/847-The-Genesis-Mission-Universities-Opportunity-to-Shape-AI-Driven-Scientific-Discovery), this update will go a long way to ensuring a smoother update. 

Full implementation will take more time. While M-25-05 expects agencies to fully integrate the DCAT-US 3.0 by the September 30th of this year, I expect that the practicalities of implementation will take longer. This is especially salient given under-resourcing and under-staffing in many CIO and CDO shops across government. Agencies can continue using DCAT US v1.1 during the transition, but the new version provides a clearer path for long term modernization. Thankfully, the new version can integrate older elements from V1.1 even if they're not officially supported (i.e., for backwards compatibility). Migration will require attention to several changes, including the requirement that `modified` be a single date, the shift to structured spatial and temporal objects, and the use of BCP 47 language tags. Agencies that begin with these elements will be well positioned to adopt the broader improvements over the long term. Critically, *agencies should adopt* DCAT-US 3.0 for all newly acquired data assets so that they do not continue to contribute to a backlog.

I'm really proud of the interagency - my OMB colleagues, the CDOC, the ICSP, and the GSA team for delivering this long-needed update. Congratulations to all who have been involved over the many years this has been in the making. 

