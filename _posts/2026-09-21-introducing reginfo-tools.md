---
layout: post
title: "reginfo-tools: A Pseudo-API Command Line Interface for Accessing Regulatory Documents and Information Collection Requests"
date: 2026-09-21
tags: [government, open data, civic tech]
---

The Office of Management and Budget's (OMB) Office of Information and Regulatory Affairs (OIRA) - my old office at OMB - maintains a website that is used to shed light on both the federal regulatory and information collection development process. It's called [reginfo.gov](reginfo.gov). The website provides basic data and information for analysis - by humans using a browser. There's no API and no straightforward way to scrape data using normal workflows. It would have been a valuable exercise for DOGE, or its OMB predecessor the USDS, to modernize reginfo.gov with a modern database and standard API for OIRA. But reginfo.gov is a sacred-cow there, and the forces of risk-aversion and workflow inertia have prevented it from becoming anything greater than a browser-based interface to OIRA data.  And there is [demand for expanded machine-access to reginfo.gov](https://github.com/regulatorystudies/) by a diverse set of stakeholders (including George Washington University's Regulatory Studies Center per that repository). In light of this antiquated position and reluctance to change the site, I put together some tools in a github repository to help with machine-access called [reginfo-tools](https://github.com/cmarcum/reginfo-tools).

# Why I built reginfo-tools

I wrote reginfo-tools to make reginfo.gov more useful to those of us doing research, policy analysis, and work evaluating government-wide information policy and rulemaking processes. The tools let users query, scrape, and download metadata and documents from reginfo.gov across both the Paperwork Reduction Act (PRA) information collection requests and Executive Order 12866 regulatory review workflows and dockets. Unlike the [George Washington University's Regulatory Studies Center toolkit](https://github.com/regulatorystudies/), it does not rely on the XML bulk data download for analysis as my repos is primarily a collection of two search and two download tools. 

In general, reginfo.gov runs on an old technstack maintained largely by one person at OIRA. There's no public API. The site relies on nested and often malformed HTML tables, fragile session states, hidden anti-forgery tokens, and document downloads triggered by JavaScript instead of standard links. In my own work, basic scraping kept failing against these quirks, so pulling together a comprehensive approach took considerable work. I ended up programmatically intercepting and passing hidden form tokens to preserve state through pagination, and using a hybrid of DOM parsing and regex to find files hidden behind the legacy frontend. 

There are four scripts so far, covering both halves of the site, plus a unified CLI. Both Gemini Pro and Claude Code helped quite a bit - but they required a lot of help with nuance of the site that I had stored in my institutional memory; I've noted where those tools come into play directly in the script comments.

## Four primary scripts

**pra-icr-search.py** maps to the PRA Search form on reginfo.gov. It handles form tokens and pagination, and includes a "Reactive Chunker" that slices a query into monthly blocks if it would otherwise exceed reginfo.gov's 1,000-result cap. For example, to pull every form discontinued government-wide during 2025:

```bash
python pra-icr-search.py dateType=DI startDate=01/01/2025 endDate=12/31/2025 --output 2025_disruptions.csv --delay 2
```

**pra-icr-download.py** takes an ICR reference number and downloads its attached documents into a named folder structure, handling duplicate filenames and inferring extensions when the server doesn't supply one. I use it like this to grab everything for a recent CDC collection:

```bash
python pra-icr-download.py 202601-0920-012 --both
```

**eo-reg-search.py** is the regulatory-review counterpart, mapping to the Search of Regulatory Review form for rules under EO 12866. It shares the same monthly chunker for large date ranges but the fields are slightly different because of nuances in database elements. Here's how I pull a year of EPA's concluded reviews:

```bash
python eo-reg-search.py agencyCode=2000 eoStatusCode=CD conclusionStartDate=01/01/2024 conclusionEndDate=12/31/2024 --output epa_2024_concluded.csv --delay 2
```

**eo-reg-download.py** takes a regulatory identification number (RIN) and pulls together everything reginfo.gov holds for it in a sensible directory tree on your local machine: View Rule snapshots across Unified Agenda cycles, RIN Data XML, review conclusion records, and EO 12866 meeting materials. Since the site requires specifying pending or concluded status, the script queries both automatically:

```bash
python eo-reg-download.py 2060-AW46 --all
```

Each pair of search and download tools has a companion codebook, codebook.md and eo-review-codebook.md, documenting the agency and status codes I use to build queries as well as all the bizarre variable codings needed for lookup. 

## Tying it together

For convenience more than anything else, I wrapped all four scripts under one helper function, `reginfo-tools.py`. This is useful so you don't have to remember which script does what. It's a thin dispatcher that executes the matching script as a subprocess with whatever arguments are passed by the user. I wrote this part with Claude Code, then tested and edited it myself.

```bash
python reginfo-tools.py icr-search agencyCode=1500 subAgencyCode=1545 icrStatus=AC --output irs_active_forms.csv --delay 2
```

Running `python reginfo-tools.py --list` prints the subcommand table, and `--help` after any subcommand passes through to that tool's own arguments.

## Getting set up

You'll need Python 3.7 or later. The main dependency is BeautifulSoup, listed in requirements.txt:

```bash
pip install -r requirements.txt
```

I built this for my own use, but I'm sharing it in case it helps anyone else trying to get structured, historical data out of a site that wasn't built for that kind of access. Let's hope that this tool isn't needed in the near future and that OIRA gets over itself and joins the age of AI and machine-actionable data. 
