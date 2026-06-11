---
layout: post
title: "Public Data Hangs in the Balance with a New Department of Commerce Policy"
date: 2026-06-11
tags: [government data, open data, information policy]
---

---

This post was written in collaboration with Meghan Maury and Beth Jarosz. A shorter, less technical, and more accessible version of this post was published by [dataindex.us](https://dataindex.us/newsletter/article/5ed3272e-9a35-4f38-881b-c62ad45d6a56) earlier today.

---

Late last week, The Department of Commerce quietly issued a sweeping policy change that has implications for literally every American. Secretary Lutnik [banned the US Census Bureau (Census) and the Bureau of Economic Analysis (BEA)](https://www.commerce.gov/opog/disclosure-avoidance-statistical-products) from certain statistical techniques that inject noise into data, especially one called ‘differential privacy’, which typically aim to protect the privacy and confidentiality of Americans and their businesses.  

## What is Differential Privacy and How is it Used?  

Differential privacy and other forms of noise infusion use math to protect individual privacy while still allowing data users to learn useful things about a group. A simple example helps explain the basic idea. Imagine a teacher wants to know how many students in a class cheated on an exam, but does not want to know which students cheated. The teacher asks each student to answer “yes” or “no” to the question, “Did you cheat on the exam?” Before answering, each student privately flips a coin. If it lands on heads, the student answers honestly. If it lands on tails, the student flips a second coin and answers “yes” for heads and “no” for tails, regardless of the truth. This protects each individual student because a “yes” could mean the student cheated, or it could just be the result of the coin flips. But because the teacher knows how much randomness was added, they can adjust for it and estimate the overall share of students who cheated.

In the Census, differential privacy works similarly to the coin-flip example by adding random "noise" to published data. This noise blends with raw data to protect individual identities. In the 2020 Census, this noise was only injected at very detailed levels, like neighborhoods or blocks, making it nearly impossible to reidentify individuals. While this can complicate research on small populations, it ensures public officials still receive accurate data for macro-level policymaking. There’s a great cartoon explanation of these tradeoffs by [Josh Neufeld here.](https://newshooks.com/news/brief-introduction-differential-privacy-2020-census) 

There are laws that govern what Census, and other statistical agencies, can and cannot do with the data they collect. For instance, Census cannot publish data that allows a respondent's identity to be inferred if it promised to keep that data confidential. Violating this law is a class-E felony for Census employees, carrying a $250,000 fine and up to five years in prison. The law is highly effective; accidental leaks are incredibly rare, and the Department of Justice has never charged a Census employee with unlawful disclosure.

At the same time, Census is required to make data "open-by-default" while increasing access to confidential data. This dual mandate \- maximizing confidentiality while increasing public access \- puts Census in a pickle. Differential privacy was a powerful tool used to solve it. You can read more about Census’s history of use of differential privacy on the Internet Archive’s Wayback Machine [capture of their page here](https://web.archive.org/web/20260524093524/https://www.census.gov/programs-surveys/decennial-census/decade/2020/planning-management/process/disclosure-avoidance/differential-privacy.html).

## Why the Change Now?

For decades, the Bureau protected privacy through "data swapping" by switching the geographic locations of similar households. Replacing this method with differential privacy for the 2020 Census sparked a firestorm among power-users. [The new method did introduce discrepancies](https://pubmed.ncbi.nlm.nih.gov/38770012/), particularly in small-area counts for rural and minority communities. It even produced some impossible results, such as occupied housing units with zero population, or age distributions that didn’t make sense in small communities. Still, Census believed that the benefits outweighed the risks and announced in June of last year that it [would continue using differential privacy for the 2030 Census.](https://web.archive.org/web/20260527104311/https://www.census.gov/newsroom/blogs/research-matters/2025/2030-census-disclosure-avoidance.html)

While the underlying motivations for the ban on differential privacy are unknown, it’s likely that years of advocacy against the use of noise-infusion (including from the [American Statistical Association](https://www.amstat.org/policy-and-advocacy/the-nation's-data-at-risk-meeting-american's-information-needs-for-the-21st-century)) combined with the interest from a [lawsuit brought against Lutnik by College Republicans in Florida](https://www.courtlistener.com/docket/71353803/university-of-south-florida-college-republicans-v-lutnick/), set the conditions for the new policy.   
The policy itself cites data-quality concerns, referencing: 

> “Statistical Policy Directive No. 1, codified at 44 U.S.C. § 3563, requires each statistical agency, as enabled by the head of the parent agency, to adopt policies, best practices, and appropriate procedures to ensure the confidentiality, accuracy, and objectivity of its statistical activities and to disseminate timely and relevant statistical products.” 

Ironically, these references were formalized into the [“Trust regulation”](https://www.ecfr.gov/current/title-5/chapter-III/subchapter-B/part-1321) issued by the Office of Management and Budget (OMB) in 2024, which actually prohibits parent agencies like the Department of Commerce from interfering with the statistical activities of statistical agencies like Census and BEA. Under the Paperwork Reduction Act of 1995, statistical policy is supposed to be coordinated by the U.S. Chief Statistician within OMB, not by Department heads

## There’s Already a Reasonable Policy Alternative “on the books”

The new policy offers only two murky alternatives to differential privacy: coarsening data (aggregating data and limiting microdata releases) or suppressing it entirely. It does not specify if data swapping is allowed. Lutknik could have used an elegant alternative already codified in policy. When OMB [issued guidance](https://whitehouse.gov/wp-content/uploads/2025/01/M-25-05-Phase-2-Implementation-of-the-Foundations-for-Evidence-Based-Policymaking-Act-of-2018-Open-Government-Data-Access-and-Management-Guidance.pdf) for implementing the OPEN Government Data Act of 2018, it addressed the concerns with the use of differential privacy in footnote 89\. Specifically, it established that any technique resulting in knowingly altered data, like differential privacy, must include: (1) clear explanations of data limitations; (2) methodological information sufficient for replication; (3) the range of uncertainty introduced; (4) instructions on how to access raw data; and (5) a statement that the data was altered solely for privacy. This guidance allowed tools like differential privacy but mandated transparency and provided a secure pathway for researchers to access raw data within Federal Statistical Research Data Centers.

## What Happens Now?

The blanket ban on all noise infusion is an unreasonable overreach that leaves the Census Bureau with a terrible choice: violate statistical laws or restrict public access to its data. Given the severe penalties for unlawful disclosure, the Bureau will almost certainly choose to limit access. Census must now clarify what techniques are allowed under the coarsening provision and define the scope of data suppression. Because this policy was issued without public consultation, the public should urge Congress to require the Department of Commerce, Census, and the Bureau of Economic Analysis to make their implementation strategies available for public comment before enacting any permanent changes that would affect the release of data.  
