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

The following is an array of hostnames that can be used to perform DNS queries to identify these servers.

##### PowerShell Manual DNS Resolution

Define a variable for the target domain.

```ps1con
$h="acme.com"
```

Create an array of remote access services or common host names.

```ps1con
$names = @("citrix", "rdp", "nvc", "vpn", "remote", "gateway", "access", "support", "anydesk", "secure-access", "remote-access", "bastion", "jump", "portal", "ctx", "netscalar", "receiver", "zscalar", "rdgateway", "rdweb", "tsgateway", "pulse", "secure", "sslvpn", "asa", "bomgar", "access", "fortigate")
```

Loop through this array. Be sure to replace `acme.com` with the primary domain for your target.

```ps1con
foreach ($n in $names){ Resolve-DnsName "$n.$h" -QuickTimeout -ErrorAction SilentlyContinue -WarningAction SilentlyContinue }
```

##### Linux Manual DNS Resolution

Define a variable for the target domain.

```zsh
h="acme.com"
```

Create an array of remote access services or common host names.

```zsh
names=("citrix" "rdp" "nvc" "vpn" "remote" "gateway" "access" "support" "anydesk" "secure-access" "remote-access" "bastion" "jump" "portal" "ctx" "netscalar" "receiver" "zscalar" "rdgateway" "rdweb" "tsgateway" "pulse" "secure" "sslvpn" "asa" "bomgar" "access" "fortigate")
```

Loop through this array. Be sure to replace `acme.com` with the primary domain for your target.

```zsh
for n in "${names[@]}"; do r=''; r=$(dig "$n.$h" +short); if [[ -n "$r" ]]; then echo $n.$h $r; fi; done
```