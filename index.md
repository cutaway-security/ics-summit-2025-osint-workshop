---
layout: default
---

# SANS ICS SUMMIT 2025
## OSINT Workshop
### Introduction

Welcome to the SANS ICS Summit 2025 OSINT Workshop. This is a two-hour event where we will walk through some basic concepts and techniques for conducting [Open Source Intelligence (OSINT)](https://www.sans.org/osint/){:target="_blank"} analysis of targets. We are going to do this analysis without loading commercial tools or tools that require accounts or API keys. But, don't let that stop you. Follow the process using your commercial, authenticated, and custom tools to do this workshop.

### Agenda and Table of Contents

* [Task 1](task1.md): Outline of the Workshop's OSINT Process
* [Task 2](task2.md): ICS / OT Passive Geolocation Reconnaissance By Sector
* [Task 3](task3.md): Student Target Identification
* [Task 4](task4.md): Start SpiderFoot Information Gathering
* [Task 5](./task5.md): Domain Name Service Exploration
  * Common Remote Access Subdomains:
    * citrix, rdp, nvc, vpn, remote, gateway, access, support, bastion, jump, portal, ctx, netscalar, receiver, zcalar, rdgateway, rdweb, tsgateway, pulse, secure, sslvpn, asa, bomgar, access, fortigate
  * AI Query for Lab servers by sector
    * "What are some names for lab analytic services and servers in the following industrial field: gas/oil, electrical, food/beverage, water/wastewater, chemical, petrochemical, Pharmaceuticals"  
  * DNSDumpster: https://dnsdumpster.com/
  * Subdomain Finder: https://subdomainfinder.c99.nl/
  * VirusTotal: https://www.virustotal.com/gui/home/search
* [Task 6](task6.md): Identify External Remote Access
  * Using Shodan.io
* [Task 7](task7.md): Document Exposure Analysis
  * Search "site:<site>.com "approved subcontractors""
  * Search ""site:<site>.com radio"
  * Search "site:<site>.com cybersecurity"
  * Search "site:<site>.com <process terms>"
  	* Emerson - DeltaV
  	* ABB - 800xA
  	* Rockwell - PlantPAx
* [Task 8](task8.md): Personnel Analysis
  * Board of Directors
  * Linked In
* [Task 9](task9.md): Email Analysis
* [Task 10](task10.md): Swagger API Analysis

## Experienced OSINT Analysts

Some of this might be basic for you. Stick with the class or move on at your own pace. Help your neighbors. Remember the leadership axiom "Train Your Own Replacement." We, your team, are stronger working together. 

## Contributors

Be sure to checkout, and thank, the [Contributors](contributors.md) to this workshop.

## Tools

We use very few tools for this workshop. You can track them on the [Tools](tools.md) page.