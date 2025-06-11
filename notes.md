---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Note Taking

For actual OSINT assessment you will need to keep detailed notes. There are many techniques and this will vary by team and client. Good note taking applications include [CherryTree](https://www.giuspen.net/cherrytree/){:target="_blank"} (installed by default in Kali), [Obsidian](https://obsidian.md/){:target="_blank"}, [Microsoft OneNote](https://www.microsoft.com/en-us/microsoft-365/onenote/digital-note-taking-app){:target="_blank"}, and [Evernote](https://evernote.com/){:target="_blank"}. Some OSINT tools may provide note taking tools in addition to being able to generate reports.

## CherryTree Note Taking

The [CherryTree](https://www.giuspen.net/cherrytree/){:target="_blank"} is installed by default in Kali. It can also be [easily installed in Windows](https://giuspen.com/cherrytreemanual/#_windows){:target="_blank"}. This note taking tool provides an excellent interface for collecting information during an assessment. Notes can be in plain text format which is excellent for cut and pasting information from terminals and websites. Notes can also be in Rich Text Format which allows for formatted data and images / screenshots.

The power of CherryTree, in the author's opinion, is in the hierarchial or tree-based note representation using [nodes](https://giuspen.com/cherrytreemanual/#_node_management){:target="_blank"}. The following bullet list is an example of tree-based nodes that could be used during this workshop.

* ACME.COM OSINT
    * Corporate Online Resources
        * Websites
        * Partner List
        * Board Members
    * Geolocation Footprint
        * International Sites
            * Canada
        * United States
            * Texas
            * California
    * Automated Tool Scanning
        * SpiderFoot
        * Recon-NG
    * DNS and Subdomain Footprint
        * Primary Name Servers
        * Subdomain Analysis
    * External Remote Access
        * VPN
        * RDP
        * Cloud Services
    * Document Exposure
        * Known Data Breaches
        * Code Repositories
    * Personnel and Email Review
        * Key Personnel
        * Email Addresses
        * Known Hacked Emails
    * External API Footprint 
        * Swagger APIs

## Reports

Good assessment reporting includes multiple sections. The following are a basic breakdown of most cybersecurity assessment deliverables. This can be modified depending on scope, client defined deliverables, automated tool reports, and unique information gathering techniques.

* Executive Summary - a brief description of the assessment goals, summary of findings, and recommendations that leadership can do to provide their team and organization with assistance for systemic and major issues.
* Methodology - a description of the scope, basic methodology tasks, tools and techniques used, and the information that was collected. The following are possible sections, similar to this workshop, that may be included in this section of the report.
    * Corporate Online Resources
    * Geolocation Footprint
    * Automated Tool Scanning
    * DNS and Subdomain Footprint
    * External Remote Access
    * Document Exposure
    * Personnel and Email Review
    * External API Footprint 
* Findings - a description of the issues identified, recommendations, and (when possible) inclusion of [MITRE ICS ATT&CK Matrix](https://attack.mitre.org/matrices/ics/){:target="_blank"} references that emphasize consequences.

## Return to Agenda
[Agenda](./index.md)