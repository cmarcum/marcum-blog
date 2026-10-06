---
layout: post
title: "We Need a New Metadata Schema for Open Research"
date: 2026-10-06
tags: [open science, open access, metadata]
---

Recently, I participated on a working group for [OpenAlex](openalex.org) that was charged with creating a set of recommendations around revising the color-coded "Open Access" system (Gold, Green, Bronze, etc). That work resulted in a report we’ve shared on Zenodo: [https://doi.org/10.5281/zenodo.21934115](https://doi.org/10.5281/zenodo.21934115) and there is a request for community feedback on the proposal and recommendation open until November 13th, 2026.

Please read the report and respond with your feedback here: [https://docs.google.com/forms/d/e/1FAIpQLSew0id7AefKryr-SGeb8DChSQkxoMUM6WP2ebmV7U3hVjuo3A/viewform?usp=publish-editor](https://docs.google.com/forms/d/e/1FAIpQLSew0id7AefKryr-SGeb8DChSQkxoMUM6WP2ebmV7U3hVjuo3A/viewform?usp=publish-editor)

You’ll see that the recommendations are tailored around what’s possible within the currently available metadata schema for published research articles. The recommendations do not address the broader issue of the need for access clarity around other artifacts (preprints, datasets, code, posters, etc). I strongly believe we need to move further than the goals of this specific project and build the metadata schema we want rather than relying on the one the publishers have built.

The color-coded "Open Access" system (Gold, Green, Bronze, etc) is an artifact of publisher-centric business models that were co-opted from earlier well-intentioned open-access movement advocates. The color system was designed by the publishers to codify revenue streams and stoke confusion among authors, institutions, and readers, drawing them away from free options of disseminating scholarly outputs. This system purposely tied "open-access" to Article Processing Charges (APCs) and double-dipping subscriptions by blending paywalls and open access in hybrid journals. The system failed to describe the actual utility, reach, or legal permissibility of a scientific output in a clear and consistent manner. Moreover, by centering primacy on the publishers' "Version of Record" (VoR) as the ultimate locus of value, the current system inherently disadvantages researchers without massive institutional funding and treats preprints, posters, and datasets as second-class artifacts.

To dismantle this, we need a metadata schema that communicates the friction experienced by the end-user (and author) and the freedoms legally granted to them, entirely agnostic to the platform or format of dissemination. We should build the metadata system that works for the community and not the one that works only for the publishers.

**Access & Licensing-Centric Approach**

Instead of a single, confusing color, every scholarly output (let’s call them “artifacts”) is assigned a standardized, machine- and human-readable schema based around how much friction an author and user experiences stemming from two dimensions: Access + Licensing. There have been other mult-dimensionsal proposals (3 in the work OpenAlex did, [6 in others](https://digitalcommons.unl.edu/cgi/viewcontent.cgi?article=1086&context=scholcom)).

*Access Dimension*

This dimension measures the technical, financial, and temporal barriers to accessing the artifact. Crucially, this dimension treats "data harvesting" (forced logins, registration, etc) as a distinct barrier, aligning heavily with FAIR principles by rewarding pure, frictionless machine-readability as well as signals/labels that are easy to understand by humans.

| **Level** | **Designation** | **Description** |  | **Examples** | 
| --- | --- | --- | --- | --- |
| **AL0** | **Unfettered** | Immediate, free access with no login required. Hosted on infrastructure that allows API/machine-readable harvesting and guarantees long-term data integrity. |  | A preprint on arXiv or a dataset in a federal repository. | 
| **AL1** | **Identity-Gated** | Free of financial cost, but requires user registration, creating a "data tax" or surveillance barrier. |  | "Read for free" after creating a publisher website account. | 
| **AL2** | **Network-Gated** | Free to the user, but contingent on their geographic location or institutional affiliation. |  | Access via university IP ranges or Research4Life waivers. | 
| **AL3** | **Time-Gated** | Currently restricted (A4 or A2) but carries a hard-coded metadata trigger to become A0 or A1 on a specific date. |  | A manuscript under a 12-month embargo. | 
| **AL4** | **Toll-Gated** | Immediate financial barrier required for access. |  | Standard subscription paywalls or $35 single-article purchases. | 

*Licensing Dimension*

This dimension communicates what a user is legally permitted to do with the object/artifact (dataset, manuscript, etc) once they have accessed it. It moves beyond the binary "Open/Closed" framework to capture the nuance of derivative works and commercial and educational reuse.

| **Level** | **Designation** | **Description** | **Examples** | 
| --- | --- | --- | --- |
| **LL0** | **Public Domain** | No rights reserved. The object can be freely used, remixed, and distributed by anyone for any purpose. | CC0, uncopyrightable government works. | 
| **LL1** | **Attribution-Reliant** | Full reuse, text-mining, and derivative rights, contingent only upon proper citation of the creators. | An academic paper appearing in a preprint repository with a CC BY license. | 
| **LL2** | **Context-Restricted** | Conditional reuse. Can be shared and adapted, but strictly limited by domain (e.g., Non-Commercial, Education-Only) or requiring downstream viral licensing (ShareAlike). | A textbook that has been licensed with CC BY-NC, CC BY-SA, custom academic-only licenses. | 
| **LL3** | **Integrity-Restricted** | Read-only. The work can be legally accessed and distributed verbatim, but no derivatives, remixes, or translations are permitted. | A dataset that does not allow subsetting or transformation and is licensed as CC BY-ND. | 
| **LL4** | **Fully Restricted** | All rights reserved. No legal right to reproduce, distribute, or text-mine without explicit, case-by-case permission. | A paywalled-article in a subscription journal with traditional copyright, full rights reserved. | 

The advantages of this two dimension system are that it is : 1) easy to communicate; 2) highly integratable into a metadata schema with a controlled vocabulary; and 3) does not attach more or less value to any specific venue or artifact. Importantly, it does not grant exceptionalism to the VoR.

I recognize that this is not an easy ask. It requires coordinated effort across the community, including indexing services, repositories, and publishers. Maybe (and I hate to say it) there is a role for AI in automagically annotating metadata. However, continuing to rely on the current color system only perpetuates confusion and reinforces structural inequities in scholarly communication. OpenAlex is right to start this effort - and still, we need to go further.

We also need to start thinking about metadata and these artifacts as living documents that require periodic updating - is it a preprint at time 1, undergoes peer review at time 2, is published at time 3, and retracted at time 4? 

Adopting a metadata framework centered on real-world access and clear licensing rights is a practical, first step toward an open research ecosystem that serves the community first. The proposal here isn’t a solution to all of the issues with the existing metadata schema - and there are probably smarter people and groups that could come up with something even better that includes better versioning information.
