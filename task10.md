---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 10: Swagger API Analysis

Applications provide the ability for the target's developers, employees, and partners to interact with different services. Some of these services may be associated with industrial control systems and may provide information about the organization, processes, assets, clients / customers, and partners. The target's online assets should be reviewed to identify any asses that are accessible to the internet.

### API Searches 

An Application Programming Interface (API) is a set of rules and protocols that allow software applications to exchange data and communicate. The API provides an interface between clients and servers to send and receive information and take actions. Your target, or their partners, may have exposed an API to the internet to improve data exchange while not realizing the risk and increased attack surface.

### Swagger Search

[Swagger](https://swagger.io/docs/specification/v2_0/what-is-swagger/){:target="_blank"} is a suite of open-source tools that follow the [OpenAPI Specification](https://swagger.io/specification/){:target="_blank"}. Swagger documentation allows teams to provide a structure of the APIs available for specific applications. These details are documented to assist develops and machines in understanding the methods and formatting of data exchanges between clients and servers using the API.

A common technique for developers is to make this information public. This allows third-party developers to create software and applications that work with the API. Openly providing this information also reduces calls to the help desk or support portals since developers, users, and machines can remotely access the information on their own. However, the API documentation may also leak useful details about private API calls and other functionality. Threat actors can use this information to identify vulnerabilities and configure an exploit using the API. These vulnerabilities may result in data access, data flow injection, remote code execution, privilege escalation, and other attacks.

1. Search your target for Swagger end points and API documentation.

    ```site:acme.com swagger```

2. Review the Swagger documentation to understand the API and its functionality.

3. Update your notes with any interesting findings.

4. Try some other Google Advanced Searches for Swagger end points:

    ```site:acme.com (inurl:"api" OR inurl:"/swagger/index.html" OR inurl:"/swagger-ui.html")```

    ```site:acme.com swagger.json```

    ```site:acme.com swagger.yaml```

### API End Points

Searches for the term `api` could return additional results. However, the `api` term can also return results associated with [American Petroleum Institute (API)](https://www.api.org/){:target="_blank"}. Hence, other methods may be required to identify the API attack surface of your target.

Return to your searches in [Task 6](task6.md) and review the results for any API related services. Inspect any services running on uncommon web ports: 1883, 3000, 5000, 8000, 8080, 8443, and 8883.

**NOTE:** Do not scan your target. We are trying to be as passive as possible.

Return to your [Task 5](task5.md) DNS and certificate results. Review the data for references to API end points.

## Next Step

When you are done, move onto [Summary](summary.md).