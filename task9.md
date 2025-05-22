---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## WARNING

We are **NOT** here to break things, people, or organizations. 
**DO NOT** [dox](https://en.wikipedia.org/wiki/Doxing){:target="_blank"} people or companies,

## Task 8: Personnel Analysis

One of the key OSINT research areas is for a target company's employees. Employees are targeted by threat actor groups because they use the internet for learning and sharing, have knowledge of the target, have the permission and ability to interact with target resources, and have relationships with other companies. Enumerating a company's employees provides a list of targets for phishing campaigns, generation of user account names, generation of email addresses, and (in the worst case) potential blackmail and extortion candidates.

### Enumerate Target Website for Employees

Companies share information about their employees by documenting organizational charts, lists of executives and directors, and publishing articles. These items can be found by manually reviewing or using Google to search the target website.

For workshop purposes, limit review of target employees to first name and last name. We'll use these for considering or generating email addresses in other tasks. We'll also use this when searching online resources, such as [LinkedIn](https://www.linkedin.com/){:target="_blank"}. 

If you are tracking personnel, consider creating a spreadsheet or Comma Separated Value (CSV) document with the following fields, if available. For actual assessments you may want to collect additional information. You can add items, such as certifications and skill sets later

* First Name
* Last Name
* Title
* Company
* Domain
* Email

1. Review the target website to identify `executives` and `board of directors`.

     * ```site:acme.com "executives"```
     * ```site:acme.com "board of directors"```
     * ```site:acme.com "advisory board"```

2. Review the target website for `organization charts`. This may be a list of actual employees (cybersecurity companies are well known for doing this), [United States Securities and Exchange Commission](https://en.wikipedia.org/wiki/U.S._Securities_and_Exchange_Commission){:target="_blank"} filings, images, media and social media articles, or leaked documents. 

     * ```site:acme.com "organization chart" OR "org chart"```
     * ```site:acme.com  "annual report" OR "quarterly report"```
     * ```site:acme.com  "meet our team"```

3. Review the target website for a list of projects or teams that may identify individuals.

     * ```site:acme.com "project management"```
     * ```site:acme.com "acceptance testing"```
     * ```site:acme.com "effective date"```
     * ```site:acme.com "scope of work"```

4. Review the target website for press releases.

     * ```site:acme.com "press release"```
     * ```site:acme.com "news-release"```
     * ```site:acme.com "in the news"```

5. Review the target's career page for employee attestations what might provide information about them.

     * ```site:acme.com "careers"```
     * ```site:acme.com "employment"```

6. Review PDF, MS Word, MS Excel documents for project documentation. These documents may name specific individuals such as project managers, engineers, operators, inspectors, safety teams, and other personnel specifically assigned to that project.

### LinkedIn Company Search

[LinkedIn](https://www.linkedin.com/){:target="_blank"} provides a wealth of information about a company and its employees. This social media site can be searched without an account but the results are extremely limited. Searching with an account will provide additional results which will ba associated with the user's account, unless privacy settings have been set on the search user's account. 

Conduct a quick search of the [LinkedIn](https://www.linkedin.com/){:target="_blank"} site for the target company's name. Review employees to find the following ICS / OT related skill sets

* Project manager
* Document manager
* ICS equipment programmer
* ICS / OT cybersecurity team
* OT network administrator
* OT windows administrator
* Control systems engineer
* Compliance, auditing, governance
* Safety engineer
* Project engineer

### Integrator Search

Most industrial and automation owner / operators partner with integrators that provide specific skill sets for their production and services. These integrators will have personnel that are allowed physical and remote access to the process environments. Identifying these integrator partners can be valuable for multiple reasons.

Use the following AI query to identify potential integrators in a specific area associated with your target. Modify the location `Texas` to match the location of your choice and the target `acme.com` to the target you are researching.

> ICS / OT environments have different system integrators for various industries and locations. Provide a thorough list of system integrators in Texas that service the acme.com.

**BE CAREFUL**: Your AI results may be _hallucinations_. You should conduct Google Advanced Searches to verify the results.

## Next Step

When you are done, move onto [Task 10](task10.md): Email Analysis.