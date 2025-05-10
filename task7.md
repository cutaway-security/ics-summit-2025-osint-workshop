---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 7: Document Exposure Analysis

The internet is for sharing information. Organizations share information with their potential customers, current clients, business partners, shareholders, and the general public. This information often includes data about current services, marketing, partnerships, personnel experience, and other information. When sharing this information there is a potential that additional data is shared unintentionally due to ignorance or misconfigurations. This data can be shared in many forms. These forms include text, HTML, PDF, MS Word, MS Excel, MS PowerPoint, XML, JSON, compressed files, and backups. These files may be found on the target's main website, other online assets, or in cloud services.

### Google Information Gathering

The [Google Advanced Search](https://www.google.co.uk/advanced_search){:target="_blank"} feature can be used to locate interesting files. Another type of search is to view a domain for specific file extensions. The following command searches the target for all files with the PDF extension (replace `acme.com` with your target site information):

```
site:acme.com ext:pdf
```

The [Exploit-DB GHDB](https://www.exploit-db.com/google-hacking-database){:target="_blank"} provides additional search terms to identify unique files with data that should not be shared publicly. We can do a `Quick Search` for the term `config` but this will only identify a few types of configuration files. To expand our list of configuration files, we can use the AI tool to identify interesting terms for Google Advanced Search. Run the following command in your AI tools and use the results to search your target for leaking configuration files.

> When using Google to identify leaking configuration files, what are some terms to use for advanced google search.

Your results should contain terms similar to: ini, conf, config, yaml, json, xml, env.

1. Conduct searches of your target for each of these file extensions.

2. Consider conducting similar searches using the `intitle`, `inurl`, and`filetype` filter terms.

3. Add any interesting results to your notes.

Use the [Exploit-DB GHDB](https://www.exploit-db.com/google-hacking-database){:target="_blank"} `Quick Search` field to run a search for these configuration file terms. 

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

## Next Step

When you are done, move onto [Task 8](task8.md): Personnel Analysis.