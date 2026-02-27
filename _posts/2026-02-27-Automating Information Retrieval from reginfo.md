---
layout: post
title: "Automating information retrieval from reginfo.gov using python scripts."
date: 2026-02-27
tags: [federal-data,code]
---

Evaluating the integrity of federal data requires a comprehensive look at how agencies collect information from the public. The primary resource for this oversight is [reginfo.gov](reginfo.gov), which hosts records on US federal information collection requests (ICRs) subject to the [Paperwork Reduction Act](https://en.wikipedia.org/wiki/Paperwork_Reduction_Act). While this database contains decades of information on agency ICRs, the site platform is based on legacy javacscript and is not conducive to large-scale interrogation.

The website lacks a public API and, as a result, large-scale data extraction is difficult and often involves iterative manual collection. One of the most restrictive limitations is a hard cap that prevents users from viewing more than 1,000 results for any single ICR search using the [PRASearch](https://www.reginfo.gov/public/do/PRASearch) tool. This limit makes it impossible to pull complete government-wide inventories without considerable manual work. Additionally, many documents are not directly linkable. They are instead hidden behind JavaScript triggers or nested within several layers of subpages, requiring significant time to locate and download individually.

To facilitate greater access to data on ICRs held by reginfo.gov, I wrote (sometimes with the help of Google Gemini) a couple of helper functions using python to overcome these limitations. The scripts and a very handy codebook are available open-source through my github here:
[https://github.com/cmarcum/pra-icr-tools](pra-irc-tools).

Feel free to contribute to the repo. While there are only two scripts available right now, I plan to add more in the future and will happily consider pull-requests that add functionality and fix any bugs. 

## Search and Metadata Extraction
The first tool in the repository, pra-icr-search.py, is a command-line script that automates the search process. It returns a csv file of search results from a query made to PRASearch. If a query hits the 1,000-result limit that reginfo.gov imposes, the script automagically detects the failure and slices the request into monthly blocks. This allows users to extract very large ICR datasets in a single execution. The script also handles hidden anti-forgery tokens and complex pagination to ensure that the data returned is accurate and complete.

Because the script handles pagination using headless javascript commands, we can collect metadata on very large ICR queries, such as this search for all concluded ICRS from the Environmental Protection Agency between 1/1/2021 and 12/31/2024:

```bash
> python pra-icr-search.py agencyCode=2000 dateType=CO startDate=01/01/2021 endDate=12/31/2024 --output epa_4_year_history.csv --delay 2
[*] Attempting primary search: {'agencyCode': '2000', 'dateType': 'CO', 'startDate': '01/01/2021', 'endDate': '12/31/2024'}
  [*] Total Records Found: 602
  [*] Scraped page 1. Rows collected: 10 (Total: 10)
  [*] Scraped page 2. Rows collected: 10 (Total: 20)
  [*] Scraped page 3. Rows collected: 10 (Total: 30)
  [*] Scraped page 4. Rows collected: 10 (Total: 40)
  [*] Scraped page 5. Rows collected: 10 (Total: 50)
  ...
  [*] Scraped page 61. Rows collected: 2 (Total: 602)
  [*] Writing 602 TOTAL records to epa_4_year_history.csv...
  [*] Complete.
```

## Automated Document Acquisition
The second tool, pra-icr-download.py, handles the physical retrieval of all manner of documents associated with an ICR. This includes the collection instruments, subparts A and B, and any public comments in the docket of supporting documents. Because agencies sometimes upload redundantly named documents to reginf.gov, the script automatically renames files with identical names to prevent them from being overwritten, ensuring that every version of a document is preserved.

To get all the current documents associated with the recent Federal Reserve Board of Governor's ICR for the [Intermittent Survey of Businesses](https://www.reginfo.gov/public/do/PRAViewICR?ref_nbr=202601-7100-005):

```bash
> python pra-icr-download.py 202601-7100-005 --both

[*] Scanning Supporting Documents for ICR 202601-7100-005...
  [*] Found 2 Supporting Documents. Downloading...
  [+] Downloaded: FR1374_20260225_omb_B.pdf
  [+] Downloaded: FR1374_20260225_omb.pdf

[*] Scanning Collection Instruments for ICR 202601-7100-005...
  [*] Discovered 1 distinct IC subpages. Traversing...
      -> Subpage 1/1 contained 1 attachments.
  [*] Found 1 total Collection Instruments. Downloading...
  [+] Downloaded: FR1374_2025_SurveyQuestions.pdf

[*] ICR file downloads complete.
```
