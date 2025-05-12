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

## Task 8: Google Email Searches

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

## Next Step

When you are done, move onto [Task 10](task10.md): Swagger API Analysis.