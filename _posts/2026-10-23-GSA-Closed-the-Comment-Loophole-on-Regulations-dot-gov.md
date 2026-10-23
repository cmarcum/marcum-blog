---
layout: post
title: "GSA Closed the Comment Count Loophole on Regulations.gov"
date: 2026-10-23
co_authors:
  - name: "Abigail Haddad"
  - url: "https://presentofcoding.substack.com/"
tags: [general]
---

In July, we [showed](https://presentofcoding.substack.com/p/no-there-arent-500000-comments-on) that anyone could inflate the  “comments received” number displayed on[ ](http://regulations.gov/)[regulations.gov](regulations.gov) – that is, the number of comments submitted during a public comment period. When you attached a file to a comment, the form asked whether the file contained comments from more than one person or entity. Check yes, and you would be asked for the “Number of persons/entities represented” by your comment. You could put any number from 1 to 999,999, and whatever number you picked would be added to the docket’s “comments submitted” count. We tested it on a[ Bureau of Land Management docket](https://www.regulations.gov/docket/BLM-2026-0068), and the count jumped from 310 to over a million by the next day.

And this topline “comments received” number drives news coverage. Reporters cited 500,000 comments on OMB’s[ proposed revisions to the Uniform
Guidance](https://www.regulations.gov/docket/OMB-2026-0034) (2 CFR 200) as a measure of public interest. The true count was still very high at over 164K, but that’s a far cry from the half million reported by the press.

Last weekend, we noticed that this had been fixed, and looked back at archived copies of [regulations.gov](regulations.gov) to see when. We found that on September 4, the General Services Administration (GSA), which runs[ regulations.gov](http://regulations.gov/), removed the question from the comment form. A week later, on September 10, GSA relabeled the count and rewrote its description. We don’t know for sure whether our post or[ the press coverage we received on it](https://www.science.org/content/article/did-500-000-people-comment-controversial-u-s-grantmaking-rule-not-likely-analysts-say) had anything to do with the decision to fix the count bug. Either way, credit to the civil servants at GSA who made the change happen. That’s good governance.

# How we know
[Regulations.gov](http://regulations.gov/) runs on a single JavaScript file that generates the comment form and the count box. Every time GSA updates the site, the file gets a new name. The Internet Archive’s Wayback Machine saves copies of those files as it crawls, so we can line up every version from the spring through today and check each one – which we did.
Every prior version we checked until midday on September 4, 2026 includes the “persons/entities” question on the comment form. Every version after does not. We were first clued into this because we noticed that, despite a very high rate of comments being submitted from campaigns to the US Census Bureau’s[ proposed rulemaking on residency requirements for the 2030 census](https://www.regulations.gov/docket/USBC-2026-0628) – a controversial rulemaking where we would expect such gaming – the comments submitted to comments published had a relatively consistent difference over time. We were tracking this because of our work on[ handsoffourcens.us](https://handsoffourcens.us/).

We investigated further to find out if GSA had indeed fixed the bug.

| Version | Saved by Wayback | Question on form? | Count description | 
| --- | --- | --- | --- |
| [e4870fb6](https://web.archive.org/web/20260904161503/https://www.regulations.gov/assets/regs-gov-e4870fb63e6a2cc104d95a28c19ab88d.js) | Sep 4, 12:15 PM ET | Yes | “as of 11:59 PM yesterday” | 
| [c583eabb](https://web.archive.org/web/20260904191438/https://www.regulations.gov/assets/regs-gov-c583eabbfdcd1ac2716db6b81d0242f4.js) | Sep 4, 3:14 PM ET | **No** | “as of 11:59 PM yesterday” | 
| [c92c9d40](https://web.archive.org/web/20260910235639/https://www.regulations.gov/assets/regs-gov-c92c9d400a3f9ab0de508f06b23c67a5.js) | Sep 10, 7:56 PM ET | No | **“including unpublished”** | 

>The new count description on the dockets is better, too. It now reads:
*“The number of comment submissions that have been received (including unpublished) to all documents within this docket.”*

## What wasn’t fixed
The counts for dockets prior to this change are still on this site. For instance, our BLM test docket still shows 1,037,743 submissions received against 4,477 posted, and the OMB docket still shows 496,606 against 164,654. Neither was corrected.

We also wanted to know whether anyone else had used the loophole before we wrote about it. So we pulled every proposed rule on[ regulations.gov](http://regulations.gov/) whose comment period closed between January 2025 and early September 2026, took a random sample of 300, and compared the number received to the number posted. Most line up closely, which is what you’d expect: the difference is usually comments an agency is still reviewing or chose not to post. A few don’t line up at all.
The standout is an FAA airworthiness directive for a single Airbus Canada aircraft model. These are technical maintenance orders that usually draw a handful of comments. This one shows 656,575 received and 4 posted. A Copyright Office rule about paying royalties through[ Pay.gov](http://pay.gov/) shows 91,510 received and none posted. We can’t prove those numbers were inflated, but we also can’t think of another way they got there.

Not every big gap reflects a user entering a large number into “persons/entities” field. Sometimes, agencies just don't post every individual comment for a mass-mail campaign, and so the posted count will remain significantly below the received count. The EPA in particular will post one representative letter to stand in for thousands of identical ones. EPA’s Waters of the United States rule, which closed October 9, shows 121,798 received and 2,095 posted in the API backend. But we can see what's driving this: the [EPA posted 47](https://www.regulations.gov/docket/EPA-HQ-OW-2026-1090) “mass comment campaign” representative records on that rule, which likely account for much of the gap.

| **Docket** | **Comment period closed** | **Received** | **Posted** | **Difference** | 
| --- | --- | --- | --- | --- |
| **Closed before the fix** |  |  |  |  | 
| [OMB-2026-0034](https://www.regulations.gov/docket/OMB-2026-0034) | Jul 13, 2026 | 496,606 | 164,654 | 331,952 | 
| [BLM-2026-0068](https://www.regulations.gov/docket/BLM-2026-0068) | Aug 14, 2026 | 1,037,743 | 4,477 | 1,033,266 | 
| [FAA-2025-0199-0008](https://www.regulations.gov/document/FAA-2025-0199-0008) | Nov 10, 2025 | 656,575 | 4 | 656,571 | 
| [COLC-2024-0004-0001](https://www.regulations.gov/document/COLC-2024-0004-0001) | Jan 13, 2025 | 91,510 | 0 | 91,510 | 
| [FWS-R4-ES-2024-0073-0001](https://www.regulations.gov/document/FWS-R4-ES-2024-0073-0001) | Jan 24, 2025 | 70,899 | 38,045 | 32,854 | 
| [EPA-HQ-OAR-2024-0419-0001](https://www.regulations.gov/document/EPA-HQ-OAR-2024-0419-0001) | Apr 15, 2025 | 20,979 | 194 | 20,785 | 
| [IRS-2025-0235-0001](https://www.regulations.gov/document/IRS-2025-0235-0001) | Oct 22, 2025 | 16,903 | 321 | 16,582 | 
| [DOT-OST-2025-0831](https://www.regulations.gov/docket/DOT-OST-2025-0831) | Aug 21, 2026 | 1,357 | 1,354 | 3 | 
| [OCC-2026-0331](https://www.regulations.gov/docket/OCC-2026-0331) | Aug 21, 2026 | 524 | 23 | 501 | 
| [EPA-HQ-OW-2026-1090](https://www.regulations.gov/docket/EPA-HQ-OW-2026-1090) | May 26, 2026 | 47 | 47 | 0 | 
| **Comment period open after the fix** |  |  |  |  | 
| [EPA-HQ-OW-2025-0322-15447](https://www.regulations.gov/document/EPA-HQ-OW-2025-0322-15447) | Oct 9, 2026 | 121,798 | 2,095 | 119,703 | 
| [FS-2025-0001-342438](https://www.regulations.gov/document/FS-2025-0001-342438) | Oct 6, 2026 | 19,826 | 19,826 | 0 | 
| [FAR-2026-0003-0001](https://www.regulations.gov/document/FAR-2026-0003-0001) | Oct 19, 2026 | 95 | 95 | 0 | 
| [OPM-2025-0012-0678](https://www.regulations.gov/document/OPM-2025-0012-0678) | Sep 29, 2026 | 81 | 76 | 5 | 
| [NRC-2025-1204-0004](https://www.regulations.gov/document/NRC-2025-1204-0004) | Oct 13, 2026 | 52 | 52 | 0 | 

>Counts pulled from the**[ regulations.gov](http://regulations.gov/)** API on October 23, 2026 (October 18 for the OMB, BLM, DOT, OCC, and EPA water docket rows). Rows linked to a docket count the whole docket. Rows linked to a document count that one comment period for a specific document within a docket.


## Methods
All data come from the public[ regulations.gov API](https://open.gsa.gov/api/regulationsgov/), the same one the website uses. “Received” is the API’s received count, and “posted” is the number of comments the API returns. The before-fix sample was drawn at random from about 2,600 whose comment periods closed between January 1, 2025 and September 3, 2026. The after-fix dockets represent every proposed rule, 35 in all, whose comment period opened September 5 or later and closed by October 22. The table shows the five largest by number received from each group, plus our original docket use-cases. Only two of the after-fix rules drew more than 100 submissions, so this sample can’t tell us much about how counts behave now. We also checked the figures against snapshots captured by Wayback Machine.

The proof of the fix is the document upload form itself: the entities count question is gone.

## What GSA should do next
We're really glad that this is fixed going forward, and we think a few small tweaks would complete the change. First, recalculate the counts on dockets where the “persons/entities” number was used, or at least flag them. Second, GSA should publish a short note explaining the change, so the public knows the count means something different now. Third, GSA should update the language about comment counts on its FAQ page,[ which is now out-of-date](https://www.regulations.gov/faq?anchor=find). We're following this issue closely, but it still took us over a month to catch this: other people who use this data might miss this important detail unless GSA points this out.