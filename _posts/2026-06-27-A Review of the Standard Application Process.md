---
layout: post
title: "A Review of the Standard Application Process"
date: 2026-06-27
tags: [statistics, government data]
--- 

<img width="975" height="148" alt="image" src="https://github.com/user-attachments/assets/d68ec8b6-3b9c-402a-b1bc-210a62278d57" />


Recently, the National Center for Science and Engineering Statistics (NCSES), which is the statistical agency at the National Science Foundation, released a new version of the [Standard Application Process (SAP) portal](http://sap.nsf.org). The SAP is intended to be the central gateway for the nation’s research community to access federal confidential statistical data assets. Required by the Foundations for Evidence-Based Policymaking Act of 2018 (specifically Title III, the Confidential Information Protection and Statistical Efficiency Act or CIPSEA), the SAP is supposed to serve as both a data catalog and a unified gateway for submitting data access applications to statistical agencies. 

The SAP was first released in late 2022 in conjunction with [OMB M-23-04](https://whitehouse.gov/wp-content/uploads/2022/12/M-23-04.pdf), which established the guidance on its use and implementation. Originally, the SAP was provided through a contract with ICPSR at a non-governmental website ([https://www.researchdatagov.org](https://www.researchdatagov.org)). The relaunch of the SAP at a governmental website [sap.nsf.gov](http://sap.nsf.gov) , through a new contract with Mathematica, represents a milestone in the federal government’s journey toward a more open, equitable, and secure public research infrastructure. However, the current implementation is a frustrating paradox: it achieves the letter of the law regarding administrative transparency while failing the spirit of the law regarding data discovery and utility. 

When I was the NCSES desk officer at OIRA I oversaw the SAP implementation. At one point, I sent NCSES a laundry list of site improvements (largely as a set of grievances with the ICPSR hosted site, and this is probably FOIAable, if you want to tango with OMB and NSF lawyers on it). These included not having, and therefore needing:

* a dot gov address \- odd for a program required in statute and overseen by OMB.  
* an easy way to see the entire catalog  
* integration with the Federal Data Catalog provided by [Data.gov](http://Data.gov)  
* ORCID IDs in the application as required by NSPM-33  
* conformity to the transparency requirements in the Evidence Act

So, how did the SAP relaunch do in achieving these features in their revision? Meh. Here’s an item-by-item account:

## A Dot Gov Address

They got this right. From a policy perspective, the transition from the legacy .org domain (researchdatagov.org) to the official sap.nsf.gov is a win. When the SAP was on my desk at OMB, I probably complained the most about this aspect to Karin Orvis (then the non-political US Chief Statistician who has been replaced by a political appointee) and John Finamore, Chief Statistician at NCSES. Not having a dot gov address is confusing to the public and is against federal policy. I'm glad they finally fixed this.

## Browsing the Whole Catalog

Apparently, Mathematica just cloned the awful interface that was originally part of [researchdatagov.org](http://researchdatagov.org). Users have to either search the catalog or, if they want to browse it, they are funneled into datasets organized by agency buckets or predefined topics, the portal prevents cross-disciplinary discovery. This is frustrating because it means that researchers are forced to know exactly which bureaucracy holds their data before they even begin. There is no mechanism to "view all" 1,498 datasets currently listed. Without a comprehensive list, the portal effectively hides nearly those assets behind a "keyword wall.”

If you want to see the whole catalog, you have use this query two double quotation marks in the search field like this:

<img width="975" height="225" alt="image" src="https://github.com/user-attachments/assets/f5ca513a-f76a-40c0-aaee-fc88813ecae8" />

Which will result in this url : [https://sap.nsf.gov/dataset/?q=](https://sap.nsf.gov/dataset/?q=%22%22)”” that can be paginated up to 100 results per page. That’s incredibly onerous and obtuse. 

You can’t even export the search results from the browser to something useable (though, you can export individual dataset metadata as individual weirdly formatted spreadsheets). 

Fret not though, since the government can't seem to provide this basic service, I've gone ahead and created [a complete inventory as a csv by scraping the entire catalog](https://github.com/cmarcum/talks-and-posts/raw/refs/heads/main/%E2%80%8E2026-06-27-A%20Review%20of%20the%20Standard%20Application%20Process/sap-catalog.csv).

## Integration with the Federal Data Catalog

As an information policy wonk, my primary concern is the new portal's inherited failure to integrate with the broader federal data ecosystem. This fails on three fronts:

1.  The law requires a "single public interface online as a point of entry" , the SAP portal currently exists as a "disconnected island" and is not linked to the Federal Data Catalog in any visible way.    
2. The SAP does not conform to the new government-wide metadata standard known as [DCAT-US 3.0](https://resources.data.gov/resources/dcat-us3/). Instead, the metadata are provided \- bizarrely \- as a spreadsheet that aren't even integrated into a single object. Each dataset has its own spreadsheet.   
3. The SAP isn't following [OMB Open Government Data Act Implementation Guidance M-25-05](https://whitehouse.gov/wp-content/uploads/2025/01/M-25-05-Phase-2-Implementation-of-the-Foundations-for-Evidence-Based-Policymaking-Act-of-2018-Open-Government-Data-Access-and-Management-Guidance.pdf). OMB was very clear in its expectations about this: 

> “The Federal Data Catalog also will provide information about how researchers and other agencies may request access to certain data assets that do not qualify as public data assets and are not appropriate for dissemination. For example, under Title III of the Evidence Act, Recognized Statistical Agencies and Units (RSAUs) accept applications to access confidential statistical data for evidence-building purposes through the Standard Application Process (SAP). The Federal Data Catalog will house the data inventory through which data assets useful for evidence building will be discovered, and it will provide information about how to access data assets through the SAP. GSA and the SAP program management office will work together to ensure that the Federal Data Catalog includes all of the necessary information and metadata for the SAP to rely upon the Federal Data Catalog for the inventory of all data assets, including confidential statistical data assets. The metadata elements of the SAP and the Federal Data Catalog are fully interoperable. Agencies with data assets included in the SAP need only create and maintain the comprehensive data inventory required under this Memorandum to satisfy the requirements of both Titles II and III of the Evidence Act. The Federal Data Catalog will be the source of metadata for the SAP.”

Without interoperability with the Federal Data Catalog and adherence to the DCAT-US 3.0 metadata standard, these confidential assets remain effectively invisible to the broader federal research community. This is a major failure that should be immediately remedied. 

# ORCID IDs

Both Federal public access and research security policies require that investigators have open persistent digital identifiers. In practice, this effectively means that ORCID IDs are mandatory. The SAP relaunch gets this right: there's now an (optional) field in the application form ([OMB control no. 3145-0271](https://www.reginfo.gov/public/do/PRAOMBHistory?ombControlNumber=3145-0271)) for researchers to enter their ORCID IDs.

# Evidence Act Transparency Requirements 

The SAP relaunch makes considerable improvements over the previous iteration on public transparency. The Evidence Act requires that the SAP make the following information publicly available:

* Each application received.  
* The status of each application.  
* The determination made for each application.  
* Any other information, as appropriate, to ensure full transparency of the process established under this subsection.

The new SAP, unlike the old version, makes the first three items very easy to see under each specific agency’s page in the portal. However, even though the “Transparency” notice on the website states that abstracts would be publicly disclosed, they are not. Here’s an example from the Bureau of Economic Analysis:

<img width="975" height="294" alt="image" src="https://github.com/user-attachments/assets/e499b609-26a5-4124-87de-4b5cccc1ad2c" />


Having abstracts publicly disclosed as expected would significantly improve the transparency of the system and how it’s being used. NCSES should fix this discrepancy by adding abstracts to the SAP immediately. 

# New Weirdnesses

Notwithstanding the mixture of enhancements over and inherited issues from the old SAP, the relaunch appears to have introduced new weirdnesses. Here are a few that I encountered: 

## Security Overkill

While security is paramount under CIPSEA, Title 13, and other statistical laws, the current implementation of the SAP introduces unnecessary friction that borders on "security overkill." The portal enforces a mandatory 16-character password requirement and two-factor authentication (2FA). This is a notably higher bar than the standard Login.gov requirement of 12 characters used for other high-security federal portals. For researchers already navigating multiple federal credentialing systems, this additional burden serves as a deterrent. Implementing security measures that exceed standard federal entry points for a metadata-browsing interface creates an unnecessary administrative hurdle that does nothing to protect the actual data, which is only accessed through separate, secure environments like the Federal Statistical Research Data Centers.

Additionally, the website is not AI-ready in any way \- agents are faced with Error 403\. This is because NCSES is enforcing robots.txt on all of its domains. You can read that here: [https://ncses.nsf.gov/robots.txt](https://ncses.nsf.gov/robots.txt) . 

It would be nice if NCSES simply used [login.gov](http://login.gov) for the SAP portal to reduce burden on applicants. Moreover, in the age of AI, it’s probably no-longer appropriate to block machine access to this resource. 

## Broken and/or Outdated Functionality?

I found a few dead-ends when exploring the new SAP. For instance, when trying to navigate to the “Datasets” tab from the landing page for the “Decennial Surname Identifiers” from Census at [https://sap.nsf.gov/dataset/doc\_census-2155](https://sap.nsf.gov/dataset/doc_census-2155), which was expected to lead to [https://sap.nsf.gov/user/metadata-records/doc\_census-2155/documents](https://sap.nsf.gov/user/metadata-records/doc_census-2155/documents), I encountered an Error 401 even though I was already logged into my account. Similarly, navigating through the nested menu in the header on the same page (Organizations ➡️  
Census Bureau ➡️ Decennial Surname Identifiers) all 401s.   

<img width="975" height="284" alt="image" src="https://github.com/user-attachments/assets/86a94c41-63e9-4e27-bee4-bee004ef03c3" />


In the application portal itself there is a massive inconsistency in the flow. The step-guide is non-linear, which could be confusing to many users. Adding a dataset to an application is really confusing. Users either have to add a dataset to their basket by browsing for it first, then they have to navigate to their basket, then they have to either start a new application or add it to an existing one. That users cannot simply add datasets directly to their existing applications *from within the application itself* is an annoying UX design flaw. 

## Missing Help Information

The Help page provides useful information about navigating the SAP. It however, does not help users know where to turn when they cannot resolve an issue on their own. For that, you have to navigate to the Contact page. Also, the “learning resources” are all PDFs, which is not the most accessible format for modern browsing. NCSES should add language to the help page referencing the contact page and add web-accessible versions of all the learning resources. 

# Conclusion

The relaunch of the SAP portal is a modest improvement over the previous iteration. Specifically, the incremental improvements include finally adopting an official dot gov domain and increased transparency regarding application status. However, the current implementation remains functionally limited. By operating as a "disconnected island" rather than integrating with the Federal Data Catalog, the portal limits efficient data discovery and is inconsistent with OMB expectations under M-25-05.

Additionally, issues such as a difficult user experience, excessive security requirements, technical bugs, and restricted machine access create unnecessary barriers for researchers. Addressing these interoperability and usability flaws is necessary for the portal to fulfill its mandate as an effective gateway for confidential statistical data. Fortunately, the changes recommended here are easy to make and I hope that NCSES will implement them soon. 
