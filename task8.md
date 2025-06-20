---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 8: Document Exposure Analysis

The internet is for sharing information. Organizations share information with their potential customers, current clients, business partners, shareholders, and the general public. This information often includes data about current services, marketing, partnerships, personnel experience, and other information. When sharing this information there is a potential that additional data is shared unintentionally due to ignorance or misconfigurations. This data can be shared in many forms. These forms include text, HTML, PDF, MS Word, MS Excel, MS PowerPoint, XML, JSON, compressed files, and backups. These files may be found on the target's main website, other online assets, or in cloud services.

**NOTE:** This section contains a lot of information. You may not get through it completely during the workshop. Quickly review each section and decide on which to prioritize before we move on. You can always come back to this.

### Google Information Gathering

The [Google Advanced Search](https://www.google.co.uk/advanced_search){:target="_blank"} feature can be used to locate interesting files. Another type of search is to view a domain for specific file extensions. The following command searches the target for all files with the PDF extension (replace `acme.com` with your target site information):

```site:acme.com ext:pdf```

The [Exploit-DB GHDB](https://www.exploit-db.com/google-hacking-database){:target="_blank"} provides additional search terms to identify unique files with data that should not be shared publicly. We can do a `Quick Search` for the term `config` but this will only identify a few types of configuration files. To expand our list of configuration files, we can use the AI tool to identify interesting terms for Google Advanced Search. Run the following command in your AI tools and use the results to search your target for leaking configuration files.

> When using Google to identify leaking configuration files, what are some terms to use for advanced google search.

Your results should contain terms similar to: ini, conf, config, yaml, json, xml, env.

1. Conduct searches of your target for each of these file extensions.

2. Consider conducting similar searches using the `intitle`, `inurl`, and`filetype` filter terms.

3. Add any interesting results to your notes.

Use the [Exploit-DB GHDB](https://www.exploit-db.com/google-hacking-database){:target="_blank"} `Quick Search` field to run a search for these configuration file terms. 

**HINT:** Here are a few more interesting file extensions:  `eml`, `bak`, `txt`, `rar`, `tar`, `zip`, `gzip`, `bzip`.

**HINT:** Run an AI query to identify file extensions for popular ICS configuration files for a specific vendor. Be sure to validate the results before you use them in your searches.

### AI Tool Search for Industrial Terms

At times, interesting information is not contained in a specific document type. The data may be directly displayed as a part of the HTML results. Additionally, searches for document types can return a lot of results and it could have been missed. Searching the target website for key process-related terms may identify interesting relationships and aid in locating leaked information.

Have your AI tool provide you with a query for common terms related to your target's industrial sector. Modify the following query example for your target.

> I am conducting OSINT research for the company `acme.com`. This company provides LNG services. What types of terms should be used to identify documentation for LNG processes and relationships with vendors and integrators? Be succinct.

The terms we received for this query included the following Google search examples. Use your results or modify these results with your knowledge of the target company's specific industry.

* ```site:acme.com "LNG process"```
* ```site:acme.com "liquefaction"```
* ```site:acme.com "regasification"```
* ```site:acme.com "LNG terminal"```
* ```site:acme.com "cryogenic"```
* ```site:acme.com "boil-off gas"```
* ```site:acme.com "safety procedures LNG"```
* ```site:acme.com "operating manual LNG"```
* ```site:acme.com "technical specifications LNG"```
* ```site:acme.com "flow diagram LNG"```

**HINT:** do not forget general cybersecurity search terms, such as: `backup`, `password`, `password`, `pwd`. If they work, they work.

Add any interesting results to your notes.

### Cloud Buckets Searches

Most organizations have turned to the cloud for services, applications, and file sharing. The configuration of these services can change from day-to-day due to normal business operations. Vendors and integrators have also started providing cloud-based services to their clients. It is possible that these services, applications, and file shares have configurations that allow direct access to the application functionality or its data.

The [Grayhat Warfare](https://grayhatwarfare.com/){:target="_blank"} tool is an online service that searches cloud services for accessible data. The tool provides the ability to search the enumerated information. This is another service that provides limited functionality for unregistered users. Unregistered users will receive a very limited number of search results. Many of these results will be image files with the file extensions PNG and JPG. The results will also include files that are associated with companies that are not your target's assets. Manual analysis will be required to determine if the data is directly or indirectly associated with your target.

Let's conduct a search for your target using the [Grayhat Warfare](https://grayhatwarfare.com/){:target="_blank"} tool.

**HINT**: These steps can be performed without registering with the search tool. If you have an account, or are willing to make one, register with the service will provide you access to more search results. It will also allow you to limit the search results using `Filename Extensions`.

1. Access the [Grayhat Warfare](https://grayhatwarfare.com/){:target="_blank"} tool and enter the target's name in the search box.

2. Click the `Search` button.

3. Review the results to determine if the data is associated with your target.

4. Conduct additional searches based on product and service names related to your target and review the results to determine if they are associated with your target's assets.

5. Add any interesting results to your notes.

### Data Leak Searches

An organization does not have to be compromised or hacked to have their data exposed in a data breach. A partner, supplier, or service provider could be breached and the data leaked may contain sensitive information about a third-party. There are many online services that provide `DarkWeb` monitoring to determine when data about an organization have been exposed. The teams for these services obtain, parse, index, and create databases of leaked information. Their service offerings often include automated notification of leaded data associated with their clients. To reduce work, threat actor groups may even be customers of these services, although they typically have access to the data via their `DarkWeb` resources.

The [Intelligence X](https://intelx.io/){:target="_blank"} provides an open source tool to search the data that their team has parsed. Searches on their site provide basic details about leaked information that may be related to a specific domain, URL, email, IP address, and other details. Reviewing the actual data does require a subscription and may be required to filter out false positives. 

1. Access the [Intelligence X](https://intelx.io/){:target="_blank"} website and enter the target's name in the search box..

2. Click the `Search` button.

3. Review the results to determine if the data is associated with your target.

4. Conduct additional searches based on product and service names related to your target and review the results to determine if they are associated with your target's assets.

5. Add any interesting results to your notes.

### Corporate SEC Reports

If a company is publicly traded then they will need to submit an [ANNUAL REPORT PURSUANT TO SECTION 13 OR 15(d) OF THE SECURITIES EXCHANGE ACT OF 1934](https://www.sec.gov/files/form10-k.pdf){:target="_blank"}. These reports can be found by searching the [U.S. Securities and Exchange Commission Search Filings tool](https://www.sec.gov/search-filings){:target="_blank"}. Since companies are expected to publish this information the reports can typically be found on a company's website under Investor Relations or About the Company. The report can show what initiatives were implemented in the past year and give insight into what has been budgeted for the following year. 

Over the years companies have discovered that these company reports should be "dressed" as a marketing tool and provide a lot of the information recommended to gather in this section into a single, visually appealing package. Unfortunately, if a company is not public you will still need to look for these items separately on their website, but they may follow suit even if they are not required to report and provide an overview report, so be on the lookout for those.

Use example reports to help identify key terms to use for search queries, such as the following:

* Food/Beverage: [Sysco 2024 Annual Report](https://investors.sysco.com/~/media/Files/S/Sysco-IR/documents/annual-reports/Sysco_2024-Annual-Report_Web.pdf){:target="_blank"}
* Equipment and Software Vendor: [ABB Integrated Report 2024](https://search.abb.com/library/Download.aspx?DocumentID=9AKK108470A7206&LanguageCode=en&DocumentPartId=&Action=Launch){:target="_blank"}
* LNG: [Cheniere Energy SEC Filings](https://lngir.cheniere.com/sec-filings){:target="_blank"}
* Distribution: [Target SEC Filings](https://corporate.target.com/investors/sec-filings){:target="_blank"}
* Industrial Machinery and Equipment: [TX Holdings SEC Filings on SEC.gov](https://www.sec.gov/cgi-bin/browse-edgar?CIK=0001133798&owner=exclude&action=getcompany&Find=Search){:target="_blank"}

Reports include the following information:

1. Business Overview
    * Risk Factors
    * Unresolved Staff Comments
    * Cybersecurity
2. Properties
3. Legal Proceedings
4. Mine Safety Disclosures
5. Market for Registrant’s Common Equity, Related Stockholder Matters and Issuer Purchases of Equity Securities
6. Reserved
7. Management Discussion and Analysis of Financial Condition and Results of Operations
    * Quantitative and Qualitative Disclosures about Market Risk
8. Financial Statements and Supplemental Data
9. Changes in and Disagreements with Accountants on Accounting and Financial Disclosures       
    * Controls and Procedures
    * Other Information
    * Disclosure Regarding Foreign Jurisdictions that Prevent Inspections
10. Directors, Executive Officers and Corporate Governance
11. Executive Compensation
12. Security Ownership of Certain Beneficial Owners and Management and Related Stockholder Matters
13. Certain Relationships and Related Transactions and Director Independence
14. Principal Accountant Fees and Services
15. Exhibit and Financial Statement Schedules
16. Form 10-K Summary

### Online Content Hosting Services

Individuals and threat actors may use online content hosting services to store and share data. These services may, or may not, provide tools to search their content. Google advance search techniques can also be used to query data on these websites. Use your search skills to search these sites for your target and related search terms.

* [Pastebin.com](https://pastebin.com/){:target="_blank"}
* [JustPaste.it](https://justpaste.it/){:target="_blank"}
* [dpaste](https://dpaste.com/){:target="_blank"}
* [GitHub Gist](https://gist.github.com/){:target="_blank"}
* [Pastesio.com](https://pastesio.com/){:target="_blank"}

### Online Development and Code Sharing Forums

Developers may share code techniques, ask, and answer questions on code development and sharing forums. The following websites can be integrated in your information gathering steps.

* [Searchcode.com](https://searchcode.com/){:target="_blank"}: A powerful source code search engine that includes results from various open-source platforms and potentially some paste sites.
* [Stack Overflow](https://stackoverflow.com/questions){:target="_blank"}: a question-and-answer website for computer programmers.
* [PLCS.net](https://www.plcs.net/){:target="_blank"}: This site offers interactive Q&A and is a source for getting free PLC programming help. It also has a forum for asking and answering PLC-related questions. 
* [Control.com](https://control.com/){:target="_blank"}: This is a large online community for controls and automation engineers where you can discuss technical and business issues. It has a PLC Archive where users can contribute or download PLC programming examples.

## Next Step

When you are done, move onto [Task 9](task9.md): Personnel Analysis.