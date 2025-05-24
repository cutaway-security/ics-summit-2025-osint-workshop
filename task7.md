---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 7: Explore External Remote Access

Threat actors will explore our external servers, including our external remote access systems. Typically this includes scanning the systems directly. However, there are several techniques to gather information about these assets without scanning them. To understand these, and to be fair to our selected targets, we are going to perform reconnaissance activities without touching the target's internet accessible servers or services. This also reduces the likelihood that the targeting will be detected by the target's administrative and cybersecurity teams.

### Google Information Gathering

Google has already indexed most of the online web services of anything connected to the internet. The [Google Advanced Search](https://www.google.co.uk/advanced_search){:target="_blank"} feature allows users to query for specific words in the webpage and to isolate searches to specific sites. A common start to search Google to identify web interfaces that prompt a user to authenticate is (replace `acme.com` with your target site information):

```site:acme.com login```

The information returned will have a combination of the target's client / customer portals and remote access services. Review these results for other useful terms to use in search filters, such as `sso`. No matter your results for these searches, it is possible that the remote access solution your target uses does not get identified by the term `login`. Why don't we ask an AI tool for some recommendations about advanced search terms? Consider running or updating the following query for your AI tool. Note that this query includes the list of remote access terms we used in [Task 6](task6.md).

> Using the following list of potential remote access solutions, what are the best google search filters to use to identify remote access services. Be succinct. "citrix", "rdp", "nvc", "vpn", "remote", "gateway", "access", "support", "anydesk", "secure-access", "remote-access", "bastion", "jump", "portal", "ctx", "netscalar", "receiver", "zscalar", "rdgateway", "rdweb", "tsgateway", "pulse", "secure", "sslvpn", "asa", "bomgar", "fortigate"

Of course, the results returned by the AI tool may have hallucinations. Update or modify the resulting filters using your own experiences. 

To leverage the experiences of many security researchers, search the [Exploit-DB Google Hacking Database (GHDB)](https://www.exploit-db.com/google-hacking-database){:target="_blank"} to confirm the syntax of the AI tool's response or to find other useful queries. Type the term in the `Quick Search` field to filter on a specific term. Be sure to add the `site:acme.com` filter to these searches to isolate your results to your target.

**HINT**: You may be able to combine queries using the `OR` operator. This would speed up the searches.

**HINT**: Why do this AI query more than once? Save your techniques to a personal cheat sheet or [Gist.github.io](https://gist.github.com/){:target="_blank"} so help speed up your future analysis efforts.

### Internet Crawler Searches

There are many online services that crawl the internet and gather information about the online assets. Some of these services allow unregistered users to search their scan results but limit the number of results, access to detailed information, and exportation of results. Registering with the service usually provides a additional functionality but limits the number of queries or access to the service's API interface.

Currently the most popular online search tools are [Shodan.io](https://www.shodan.io/){:target="_blank"}, [Censys](https://censys.io/){:target="_blank"}, [Hunter Search Engine](https://hunter.how/), and [FOCA](https://en.fofa.info/){:target="_blank"}. Each search tool provides information is a slightly different results format and reporting output. Let's review each service to see the information that is returned by the tool for the remote access servers identified in the previous tasks. You can also search on the target's external subnets if it was identified using ASN data.

**HINT**: These steps can be performed without registering with the search tool. If you have an account, or are willing to make one, register with the service to see the additional functionality the tool provides.

1. Conduct a search using the FQDN or IP address for the remote access server identified in previous tasks.

2. Review the results to determine if the listening services provide any details about the service and the target company. 

3. Review the results to determine if the search tool identifies known vulnerabilities in the listening services or operating system. Add this information to your notes.

4. If your target has a range of external IP addresses, conduct the search again using the IP range. Note any additional remote access services or ICS / OT assets in this data.

## Next Step

When you are done, move onto [Task 8](task8.md): Document Exposure Analysis.