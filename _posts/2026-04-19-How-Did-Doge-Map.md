---
layout: post
title: "How Did DOGE Cuts Hit Your State?"
date: 2026-04-19
tags: [general, open science]
---

My friend [Abigail Haddad](https://www.linkedin.com/in/abigail-haddad/) has been doing amazing things with open government data. Her website is a [treasure trove of data science workflows](https://abigailhaddad.netlify.app/) that give insights into the federal administrative state on topics as diverse as public comment analysis in rulemaking and the status of federal job openings.

In a recent project, Abigail pulled bulk data from [usaspending.gov](usaspending.gov) on nearly [70,000 federal contract cancellations](https://terminations.vercel.app/) that occurred in the last year. The vast majority of the contracts canceled were done so with the justification that they were "terminated for convenience" to the government. 

As we all now know, DOGE pushed agencies to cancel large numbers of federal contracts by directing them to end agreements it viewed as wasteful or misaligned with the administration’s agenda - or because [ChatGPT told them they were](https://www.advocate.com/politics/national/doge-chatgpt-dei-lgbtq-grants). Agency staff responded by issuing termination notices, often without providing detailed justification, and contractors later alleged that these cancellations were driven by political motives rather than performance issues. Sometime last year, I was trying to do information quality checks on the assertions DOGE was making on its stupid government website about how much they had canceled (site is not even worth linking to here) by reviewing actual contracts available through the [Federal Procurement Data System](https://www.fpds.gov/common/html/public_welcome_text.html) and I was noting that many contract cancellations were in fact tagged with the "convenience" justification. A few of those were also annotated by the procurement officer as "ordered by DOGE" or just "DOGE." 

Abigail's work provides a richer perspective on the contract cancellations than most of the press covered, or that I was able to gain insight to through FPDS earlier on in the chaos. Because she conveniently provided the data (repackaged from usaspending in a more convenient format), we can ask questions of interest using these data. For instance, I wanted to know which states were most impacted by the contracts terminated for convenience to the government. Using [a bit of R-code](https://github.com/cmarcum/talks-and-posts/blob/main/2026-04-19-How-Did-Doge-Map/doge_map.R), that was really easy to accomplish thanks to Abigail's work. Here's the result:

<div class="map-container" style="margin: 20px 0;">
  <iframe 
    src="{{ '/assets/leaflets/2025spending.html' | relative_url }}" 
    width="100%" 
    height="600px" 
    style="border: none; border-radius: 8px; box-shadow: 0 4px 8px rgba(0,0,0,0.1);" 
    title="Choropleth of Federal Contract Cancellations, 2025-2026">
  </iframe>
</div>
