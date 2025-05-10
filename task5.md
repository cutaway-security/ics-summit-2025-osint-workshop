---
layout: default
---

# OSINT Workshop
[Agenda](./index.md)

## Task 5: Domain Name Service Exploration

Companies provide public information about their sites and services using [Domain Name Service (DNS)](https://en.wikipedia.org/wiki/Domain_Name_System){:target="_blank"} so that people do not need to remember an Internet Protocol (IP) address. A company's website may be configured with the Fully Qualified Domain Name (FQDN) setting similar to `www.acme.com`. The company's online store FQDN may be `store.acme.com`. However, the server's IP address is required by the application, such as a web browser, to interact with the service. The application requests the IP address for a host or service by making a DNS query to a DNS server. The DNS server's response will contain the current IP address for the targeted domain. 

For ICS / OT OSINT analysis, performing DNS reconnaissance is important because the companies external DNS may provide details about the techniques use to provide remote access, monitoring, and possibly control. DNS information may also provide details about the IP ranges for the company's corporate and control environments instead of their cloud-based assets. DNS may also provide references to industrial projects and capabilities that are not publicly promoted but do contain information about the control network and operations.

### Query Remote Access Host Names

Every company needs to provide remote access for their workforce. ICS / OT companies may need to provide access to their control environments to vendors, integrators, partner companies, and other business units. There are a large number of remote access techniques and technologies. The host names for these assets often follow a naming scheme that is common to the remote access technique or technology. For example, Citrix services could be hosted on a server with the hostname `citrix` or the abbreviation `ctx`. For the ACME domains this would require a DNS record for `citrix.acme.com` or `ctx.acme.com` which points to the IP address for the server. 

#### AI Challenge

Use the following, or a similar query, to ask your AI tool to list some remote access service host names.

> ICS / OT environments allow remote access via different types of services and servers. Provide a list of server hostnames that may be used by the top remote access solutions to these environments. Be succinct but provide at least fifteen hostnames for the acme.com domain.

#### Array of Remote Access Server Hostnames

The following is an array of hostnames that can be used to perform DNS queries to identify these remote access servers. We can use this list to perform DNS searches using Windows or Linux tools.

> "citrix", "rdp", "nvc", "vpn", "remote", "gateway", "access", "support", "anydesk", "secure-access", "remote-access", "bastion", "jump", "portal", "ctx", "netscalar", "receiver", "zscalar", "rdgateway", "rdweb", "tsgateway", "pulse", "secure", "sslvpn", "asa", "bomgar", "fortigate"

There are automated tools that can search for these server names. However, we should have the skills to conduct manual searches for this information, when those tools are not available. Let's use some Windows and Linux command line tools to manually request DNS information for the target company's remote access servers.

##### PowerShell Manual DNS Resolution

The following commands can be copied into a PowerShell terminal.

1. Define a variable for the target domain. Be sure to replace `acme.com` with the primary domain for your target.

    ```ps1con
    $h="acme.com"
    ```

2. Create an array of remote access services or common host names.

    ```ps1con
    $names = @("citrix", "rdp", "nvc", "vpn", "remote", "gateway", "access", "support", "anydesk", "secure-access", "remote-access", "bastion", "jump", "portal", "ctx", "netscalar", "receiver", "zscalar", "rdgateway", "rdweb", "tsgateway", "pulse", "secure", "sslvpn", "asa", "bomgar", "fortigate")
    ```

3. Loop through the array, collect the results, and print anything that returned an IPv4 address.

    ```ps1con
    $results = @()
    foreach ($n in $names){ $results+=(Resolve-DnsName "$n.$h" -DnsOnly -QuickTimeout -ErrorAction SilentlyContinue -WarningAction SilentlyContinue); }
    foreach ($r in $results){ if ($r.IP4Address) { Write-Host $r.Name $r.IP4Address } }
    ```

4. Add the results to your DNS notes.

##### Linux Manual DNS Resolution

There are many ways to do DNS queries in Linux, particularly penetration testing virtual machines like Kali linux. Common tools include [dig](https://en.wikipedia.org/wiki/Dig_(command)){:target="_blank"}, [nslookup](https://en.wikipedia.org/wiki/Nslookup){:target="_blank"}, [host](https://en.wikipedia.org/wiki/Host_(Unix)){:target="_blank"}, [dnsrecon](https://github.com/darkoperator/dnsrecon){:target="_blank"}, and others. 

1. Define a variable for the target domain. Be sure to replace `acme.com` with the primary domain for your target.

    ```zsh
    h="acme.com"
    ```

2. Create a list of remote access services or common host names.

    ```zsh
    names=("citrix" "rdp" "nvc" "vpn" "remote" "gateway" "access" "support" "anydesk" "secure-access" "remote-access" "bastion" "jump" "portal" "ctx" "netscalar" "receiver" "zscalar" "rdgateway" "rdweb" "tsgateway" "pulse" "secure" "sslvpn" "asa" "bomgar" "fortigate")
    ```

3. Loop through the list, collect the results, and print anything that returned an IPv4 address.

    ```zsh
    for n in $names; do host "$n.$h" | grep -v -e "not found" -e alias -e handled | cut -d' ' -f1,4; done 
    ```

4. Add the results to your DNS notes.

### Identify Target Company Subdomains

The target company may not use these host names for remote their remote access servers. It would also be useful to understand if there are any external servers related to ICS / OT services. There are several online tools that can provide information about a domain's subdomains. These tools gather internet DNS information without enumerating DNS using brute force techniques.

#### DNSDumster Search

The [DNSDumpster](https://dnsdumpster.com/){:target="_blank"} tool will provide a lot of valuable information about a target domain. The data returned for each identified host includes FQDN, IP address, [Autonomous System Number (ASN)](https://en.wikipedia.org/wiki/Autonomous_system_(Internet)){:target="_blank"}, ASN Name, and Open Services. The results, however, are limited to the first fifty results for free queries.

1. Access the [DNSDumpster](https://dnsdumpster.com/){:target="_blank"} website in your web browser.

2. Enter the target's domain, such as `acme.com`, into the field labeled `Enter a Domain to Test`.

3. Press the `Start Test!` button.

4. Review the results and add relevant information about ICS / OT related hosts to your notes. Export the results to XLSX, if you prefer.

5. Review the ASN Name field to determine if any of the ASN numbers are directly tied to the target company. Confirmation may require additional analysis. For the associated ASNs, note the IP ranges identified by ASN numbers. 

#### Subdomain Finder Search

The [Subdomain Finder](https://subdomainfinder.c99.nl/){:target="_blank"} tool will provide information about subdomains for the target's domain. Scan results using this tool include information about the FQDN, IP address, and if the [CloudFlare](https://en.wikipedia.org/wiki/Cloudflare){:target="_blank"} service was detected. The results also include a summary of the IP addresses, a list of subdomains without IP addresses, and (interestingly) the results of previous scans.

1. Check the `Private Scan` to prevent the scan from being logged and indexed. 

2. Add the target's domain to the textbox labeled `Domain (eg. example.com)`.

3. Press the `Start Scan` button.

4. Review the results. Extract them by copying to the clipboard or downloading the CSV or JSON file.

FUTURE TESTING: The tool provides the ability to `Check Status` for each of the subdomains. Clicking on the `Check Status` button enables the `Status` column. Each FQDN needs to be check individually by clicking the `Check` button.

### Certificate Analysis

Online services require secure communications. These secure communications require Transport Security Layer (TLS) certificates that are associated with the company's domain. Most organizations will generate a specific certificate for each online asset rather than using a wildcard certificate to cover all of the first-level subdomains. A search for issued certificates can provide details about online asset like remote access servers.

The online tool [crt.sh](https://crt.sh/){:target="_blank"}, by [Sectigo](https://www.sectigo.com/){:target="_blank"}, maintains a list of issued certificates over time. It can be used to list all of the certificates for a specific target. 

1. Access the [crt.sh](https://crt.sh/){:target="_blank"} site and enter your target's domain into the search text box.

2. Click the `Search` button.

3. Review the results and add relevant information about ICS / OT related hosts to your notes. Export the results to XLSX, if you prefer.

### Reverse DNS Lookup

Manual reverse DNS lookups can be performed using the previous techniques. An easier tool to use is [DNSRecon](https://github.com/darkoperator/dnsrecon){:target="_blank"}. The [DNSRecon tool is available in the Kali distribution](https://www.kali.org/tools/dnsrecon/){:target="_blank"} or it can be installed following the [installation instructions](https://github.com/darkoperator/dnsrecon/wiki/Installation-Instructions){:target="_blank"}.

If the DNS analysis resulted in a range of IP's for the target company, consider performing a reverse DNS lookup. Run the following steps on your testing system with DNSRecon installed.

1. Start a terminal.

2. Run the command `dnsrecon -r x.x.x.x/24` replacing the value `x.x.x.x/24` with the IP range from the ASN information or other identifying information.

3. Review the `PTR` results and add interesting FQDNs and IP addresses to your notes.

### Questions to Answer

1. How many subdomains does the organization have?
2. Are any of these subdomains for test servers or remote access?
3. Were any API endpoints identified?
4. Did you get a list of known email addresses?

## Next Step

When you are done, move onto [Task 6](task6.md): Identify External Remote Access.