---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 9: Email Analysis

In the previous steps you may have identified the format the target company uses for email addresses. Understanding the email domain is important. Some companies use their primary domain. Other companies might add an extension, such as `acme-llc.com`. The user's account name will also have a variety of formats. These can be a combination of first name, first initial, last name, initials, and any combination of the concatenated values.

The following steps are designed to identify a user's email address for the target company. Once a few emails have been identified, it is only a matter of scripting to generate a full list of email addresses for known employees.

## WARNING

We are **NOT** here to break things, people, or organizations. 
**DO NOT** [dox](https://en.wikipedia.org/wiki/Doxing){:target="_blank"} people or companies,

### Google Email Searches

Google is always a good place to start. Try these tricks on other search engines for different results.

### Exploit-DB GHD Review

Emails have been around for a long time. There are most likely common Google Advanced Search techniques to identify leaked emails for our target companies.

1. Access the [Exploit-DB GHD]() page and type `email` in the `Quick Search` (the search is automatic).

2. Review the results and note any searches you would like to perform on your target domain or on the internet in general. 

3. Repeat this review using the following terms in the `Quick Search`: `credentials`, `@`, `accounts`

4. Review the results and note any searches you would like to perform on your target domain or on the internet in general.

5. Run your searches and note any results in your personnel tracking document.

### AI Tools Email Search

Formatting the advanced search filters for online search engines can be a challenge. Especially when considering the different types of email address obfuscation techniques user use to hide their emails from search engines. But, humans are predictable. Let's see if your AI tool can help in this situation. Try this search in your AI search tools. Update the query if you think it helps.

> When conducting a penetration test to identify OSINT leakage, what is a good google advanced search (google dork) to identify the email format for a company's email and to located email address that may have been entered in online forums? Include methods to detect if the user obfuscated the email using spaces, parenthesis, brackets, and other common methods. Be succinct.

Your results may be similar to the following for searching your target's website. This may return limited information, if any.

```site:acme.com (*@acme.com OR "[at]acme.com" OR "(at)acme.com" OR "{at}acme.com" OR " at acme.com")```

Searching specific forums can be done as well. Forums specializing in industrial and automation control include: [Control.com DCS](https://control.com/forums/forums/distributed-control-systems-dcs.30/){:target="_blank"}, [ADD DCS Community](https://new.abb.com/control-systems/community){:target="_blank"}, [PLCTalk](https://www.plctalk.net/){:target="_blank"}, [Mr.PLC](https://mrplc.com/){:target="_blank"}, etc. Share others with your neighbors.

```site:onlineforum.com (*@acme.com OR "[at]acme.com" OR "(at)acme.com" OR "{at}acme.com" OR " at acme.com")```

Or, you can just search the whole internet. This may return many results and 

```(*@acme.com OR "[at]acme.com" OR "(at)acme.com" OR "{at}acme.com" OR " at acme.com")```

### Emails in Breach Disclosures

Users are known to use their corporate email addresses to create accounts on the internet. Most of the time these users are interacting with vendors and integrators websites for which they have legitimate business. Other times, these users are using the data on internet forums or cloud services for industry related knowledge or associations. In the worst case, these users are using their corporate emails on elicit sites to avoid their partners and family from knowing they are involved in these activities. 

In all cases, these third-party sites can be hacked and their data distributed to the internet. These third-party disclosures are commonly referred to as data breaches. Once the data from a breach has been exposed to the internet it is accessible to everyone on the internet. While it seems easy to download and search this information the steps for obtaining, parsing, storing, and maintaining this information can be tedious and expensive.

Services have started to collect this information and provide access to the data for users to determine if their credentials have been exposed. The tool [Have I Been Pwned (HIBP)](https://haveibeenpwned.com/){:target="_blank"} maintains a website where a user can review their individual accounts to determine if an email address was associated to any data breaches. The search tool will return information about the email address provided and all of the data breaches with which it is associated. This allows the user to know if their data and credentials can be obtained and used by threat actors. The service also allows organizations to register to be able to search and monitor their company accounts.

Other companies have followed [HIBP's](https://haveibeenpwned.com/){:target="_blank"} approach to providing users with this information. Many of these services allow for enumeration of this information using a subscription service to access their data using an API key. OSINT tools user these services, typically requiring an API key, to search for the target's users and identified emails in known data breaches. For example, the [SpiderFoot](https://github.com/smicallef/spiderfoot){:target="_blank"} tool has a plugin named [sfp_citidel](https://github.com/smicallef/spiderfoot/blob/master/modules/sfp_citadel.py){:target="_blank"}. The [sfp_citidel](https://github.com/smicallef/spiderfoot/blob/master/modules/sfp_citadel.py){:target="_blank"} plugin is configured to use the data breach search site [Leak - Lookup](https://leak-lookup.com/){:target="_blank"}. This plugin is automatically selected to run during the SpiderFoot - Passive scan, which you may have started during [Task 4](task4.md).

Search your SpiderFoot - Passive scan for hacked emails.

1. Find your SpiderFoot scan in the web browser and select the scan.

2. Locate the tab named `Browse` and click on it.

3. In the `Type` column, locate the item named `Hacked Email Address` and click on the link.

4. The displayed results should show user email addresses in the column labeled `Source Data Element`.

5. Information in the `Data Element` column includes the email address plus the common name for the data breach that leaked the information. 

    **NOTE:** The name of the breach can be reviewed to determine the type of credential data that was exposed in that data breach.

6. Note any results in your personnel tracking document.

7. Review the `Browse` tab and locate other modules with `email` in the name. Click on each and review contents.

8. Note any results in your personnel tracking document.

## Next Step

When you are done, move onto [Task 10](task10.md): Swagger API Analysis.