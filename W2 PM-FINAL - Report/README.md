
# 🛡️ Week 2 — Cybersecurity Reconnaissance & Network Scanning

**Networkwalks Cybersecurity Internship — Batch B083 | Week 2**

> **Phase 1: Reconnaissance & Footprinting**  
> **Phase 2: Scanning & Network Discovery**

---

# 📌 Project Overview

This Week 2 project focuses on practical **cybersecurity reconnaissance, OSINT, footprinting, and network discovery** activities performed using Kali Linux security tools.

The project was divided into three completed modules:

- **PM1 — Kali Linux Footprinting**
- **PM4 — theHarvester OSINT Aggregation**
- **PM5 — Zenmap Local Network Scanning**

The activities covered both external reconnaissance concepts and local network discovery.

The purpose of this project was to understand how information can be collected during the early stages of a penetration testing workflow and how reconnaissance results can be documented and analyzed from a security perspective.

---

# 🎯 Project Objectives

The main objectives of Week 2 were:

- Understand the reconnaissance and footprinting phase.
- Learn practical Kali Linux reconnaissance tools.
- Collect publicly available information about domains.
- Identify technologies and infrastructure information.
- Perform OSINT aggregation using theHarvester.
- Identify publicly indexed email addresses and subdomains.
- Discover active hosts on a local network.
- Visualize network topology using Zenmap.
- Understand how reconnaissance contributes to attack-surface mapping.
- Document findings professionally.
- Follow authorized and ethical security-testing practices.

---

# 🧩 Modules Completed

| Module | Topic | Phase | Status |
|---|---|---|---|
| PM1 | Kali Linux Footprinting | Phase 1 | ✅ Completed |
| PM4 | theHarvester OSINT Aggregation | Phase 1 | ✅ Completed |
| PM5 | Zenmap Local Network Scanning | Phase 2 | ✅ Completed |

---

# 🛠️ Tools Used

The following tools were used during the project:

| Tool | Purpose |
|---|---|
| WHOIS | Domain registration information |
| WhatWeb | Technology fingerprinting |
| Nslookup | DNS resolution |
| cURL | HTTP header analysis |
| WAFW00F | WAF detection |
| DNSRecon | DNS enumeration |
| theHarvester | OSINT aggregation |
| Zenmap | Network discovery and visualization |
| Nmap | Host discovery |

---

# 🔬 Overall Methodology

The overall workflow followed during Week 2 was:

```text
Reconnaissance
      ↓
Footprinting
      ↓
Technology Identification
      ↓
DNS Enumeration
      ↓
OSINT Collection
      ↓
Network Discovery
      ↓
Host Identification
      ↓
Network Topology Mapping
      ↓
Security Analysis
      ↓
Documentation
```

---

# 🔎 PM1 — Kali Linux Footprinting

## 📌 Module Overview

PM1 focused on using Kali Linux reconnaissance tools to collect information about the target domain.

The activity included:

- WHOIS enumeration
- Web technology fingerprinting
- DNS resolution
- HTTP header analysis
- WAF detection
- DNS enumeration

### Target

```text
networkwalks.com
```

---

# 💻 PM1 Activities

## Activity 1 — WHOIS Enumeration

### Tool Used

```text
WHOIS
```

### Command

```bash
whois networkwalks.com
```

### Result

WHOIS enumeration provided domain registration and registrar-related information.

The registrar information identified during the activity included:

```text
GoDaddy
```

### Security Relevance

WHOIS information can help identify:

- Domain registration details
- Registrar information
- Domain ownership-related information
- Reconnaissance information useful during assessment

### Screenshot Evidence

![WHOIS Enumeration](../W2%20PM1%20-%20Kali%20Linux%20Footprinting/01-whois.png)

---

## Activity 2 — WhatWeb Technology Fingerprinting

### Tool Used

```text
WhatWeb
```

### Command

```bash
whatweb networkwalks.com
```

### Result

Technology fingerprinting identified information related to the web application and server infrastructure.

Observed technologies included:

```text
WordPress 7.0.4
WP Download Manager 3.3.58
Apache
```

### Security Relevance

Technology fingerprinting can help identify:

- Web application technologies
- CMS platforms
- Plugins
- Server technologies
- Potential areas requiring further security assessment

### Screenshot Evidence

![WhatWeb Technology Fingerprinting](../W2%20PM1%20-%20Kali%20Linux%20Footprinting/02-whatweb.png)

---

## Activity 3 — DNS Resolution

### Tool Used

```text
Nslookup
```

### Command

```bash
nslookup networkwalks.com
```

### Result

DNS resolution provided IP-related information for the target domain.

The identified IP address was:

```text
192.232.216.135
```

### Security Relevance

DNS information can help security professionals understand the external infrastructure associated with a domain.

### Screenshot Evidence

![Nslookup DNS Resolution](../W2%20PM1%20-%20Kali%20Linux%20Footprinting/03-nslookup.png)

---

## Activity 4 — HTTP Header Analysis

### Tool Used

```text
cURL
```

### Command

```bash
curl -I https://networkwalks.com
```

### Result

HTTP response headers were collected from the target website.

The headers provided information about the web server and HTTP response behavior.

### Security Relevance

HTTP headers can reveal useful information about:

- Server technologies
- Web application behavior
- Security-related headers
- HTTP response configuration

### Screenshot Evidence

![cURL HTTP Headers](../W2%20PM1%20-%20Kali%20Linux%20Footprinting/04-curl.png)

---

## Activity 5 — WAF Detection

### Tool Used

```text
WAFW00F
```

### Command

```bash
wafw00f https://networkwalks.com
```

### Result

The activity identified information indicating the presence of:

```text
ModSecurity
SpiderLabs
```

### Security Relevance

Identifying a Web Application Firewall provides useful information about the defensive technologies protecting a web application.

### Screenshot Evidence

![WAFW00F WAF Detection](../W2%20PM1%20-%20Kali%20Linux%20Footprinting/05-wafw00f.png)

---

## Activity 6 — DNS Enumeration

### Tool Used

```text
DNSRecon
```

### Command

```bash
dnsrecon -d networkwalks.com
```

### Result

DNS enumeration identified DNS infrastructure information.

Observed information included:

```text
mail.networkwalks.com
```

as well as cPanel-related service records.

### Security Relevance

DNS enumeration can help identify:

- Mail infrastructure
- Service records
- Subdomains
- External DNS configuration
- Additional attack-surface information

### Screenshot Evidence

![DNSRecon Enumeration](../W2%20PM1%20-%20Kali%20Linux%20Footprinting/06-dnsrecon.png)

---

# 📊 PM1 Findings Summary

| Finding | Observation | Security Relevance |
|---|---|---|
| Registrar | GoDaddy | Provides domain registration information |
| CMS | WordPress 7.0.4 | Technology information exposed |
| Plugin | WP Download Manager 3.3.58 | Additional application information |
| Web Server | Apache | Server technology identified |
| IP Address | `192.232.216.135` | Infrastructure information |
| WAF | ModSecurity / SpiderLabs | Defensive technology identified |
| DNS | Mail and service records | Additional infrastructure information |

> These findings are reconnaissance observations and should not be interpreted as confirmed vulnerabilities.

---

# 🔎 PM4 — theHarvester OSINT Aggregation

## 📌 Module Overview

PM4 focused on collecting publicly available information using **theHarvester**.

The activity demonstrated how search engines and OSINT sources can provide information about a target domain.

### Target

```text
microsoft.com
```

### Primary Source

```text
Baidu
```

---

# 💻 PM4 Activities

## Activity 1 — theHarvester Help and Tool Understanding

### Command

```bash
theHarvester -h
```

### Result

The help menu displayed available theHarvester options and supported OSINT sources.

The options included functionality for:

- Domain enumeration
- Source selection
- Result limits
- DNS resolution
- API-based sources
- Proxy configuration
- Screenshot options

### Security Relevance

Understanding the available options helps perform OSINT reconnaissance in an organized manner.

### Screenshot Evidence

![theHarvester Help](../W2%20PM4%20-%20theHarvester%20OSINT/01-theharvester-help.png)

---

## Activity 2 — Baidu OSINT Enumeration

### Command

```bash
theHarvester -d microsoft.com -b baidu
```

### Result

TheHarvester successfully searched for publicly indexed information related to:

```text
microsoft.com
```

The activity identified:

```text
Emails found: 1
Hosts found: 4
```

One email address identified was:

```text
viva.noreply@microsoft.com
```

The identified hosts included:

```text
hxd.research.microsoft.com
schannels.microsoft.com
t.msn.microsoft.com
watson.microsoft.com
```

### Security Relevance

Publicly indexed email addresses and subdomains can provide useful information during reconnaissance.

They may help security professionals understand:

- External infrastructure
- Public resources
- Domain naming conventions
- Potential attack-surface areas

These findings are reconnaissance observations and not confirmed vulnerabilities.

### Screenshot Evidence

![theHarvester Baidu Results](../W2%20PM4%20-%20theHarvester%20OSINT/02-theharvester-baidu-results.png)

---

## Activity 3 — Multiple OSINT Sources

### Command

```bash
theHarvester -d microsoft.com -b all
```

### Result

TheHarvester attempted to query multiple available OSINT sources.

The output showed that several sources required API keys.

Examples included:

```text
BeVigil
Bing
Bufferoverun
DNSDumpster
GitHub
Hunter
SecurityTrails
Shodan
VirusTotal
```

### Security Relevance

Using multiple OSINT sources can provide broader reconnaissance coverage.

However, missing API keys can limit the amount of information that can be collected.

### Screenshot Evidence

![theHarvester API Sources](../W2%20PM4%20-%20theHarvester%20OSINT/03-theharvester-api-sources.png)

---

# 📊 PM4 Findings Summary

| Finding | Observation | Security Relevance |
|---|---|---|
| Target | `microsoft.com` | Domain used for OSINT exercise |
| Email | `viva.noreply@microsoft.com` | Publicly indexed email |
| Hosts | 4 identified | Reveals additional infrastructure |
| Subdomain | `hxd.research.microsoft.com` | Publicly indexed resource |
| Subdomain | `schannels.microsoft.com` | Publicly indexed host |
| Subdomain | `t.msn.microsoft.com` | Publicly indexed host |
| Subdomain | `watson.microsoft.com` | Publicly indexed host |
| OSINT Source | Baidu | Public search information |
| API Sources | Multiple | Additional sources available with API keys |

> These findings represent publicly available reconnaissance information and are not confirmed vulnerabilities.

---

# 🖥️ PM5 — Zenmap Local Network Scanning

## 📌 Module Overview

PM5 focused on **local network discovery and network topology visualization** using Zenmap.

Zenmap was used as the graphical interface for Nmap.

### Target Network

```text
10.0.0.0/24
```

### Scan Profile

```text
Ping Scan
```

### Nmap Command

```bash
nmap -sn 10.0.0.0/24
```

---

# 💻 PM5 Activities

## Activity 1 — Local Network Ping Scan

### Objective

Identify active hosts within the local virtual network.

### Target

```text
10.0.0.0/24
```

### Result

The scan identified **3 active hosts**:

```text
10.0.0.1
10.0.0.2
10.0.0.254
```

The scan output reported:

```text
Nmap done: 256 IP addresses (3 hosts up)
```

The scan also displayed MAC address information for the discovered VMware hosts.

### Security Relevance

Host discovery is an important part of network reconnaissance.

It helps identify:

- Active systems
- Network size
- Potential targets for further assessment
- Virtual network infrastructure

### Screenshot Evidence

![Zenmap Ping Scan](../W2%20PM5%20-%20Zenmap%20Local%20Network%20Scanning/01-zenmap-ping-scan.png)

---

## Activity 2 — Network Topology Visualization

### Objective

Visualize the discovered hosts and their relationship with the local system.

### Tool Used

```text
Zenmap Topology
```

### Result

The topology view displayed the local system and discovered hosts.

The network visualization included:

```text
localhost
10.0.0.1
10.0.0.2
10.0.0.254
```

### Security Relevance

Network topology visualization can help security professionals understand:

- Network structure
- Connected systems
- Host relationships
- Potential areas for further assessment

### Screenshot Evidence

![Zenmap Network Topology](../W2%20PM5%20-%20Zenmap%20Local%20Network%20Scanning/02-zenmap-network-topology.png)

---

# 📊 PM5 Findings Summary

| Finding | Observation | Security Relevance |
|---|---|---|
| Target Network | `10.0.0.0/24` | Local network scanned |
| Scan Type | Ping Scan | Used for host discovery |
| Active Host | `10.0.0.1` | Active system identified |
| Active Host | `10.0.0.2` | Active system identified |
| Active Host | `10.0.0.254` | Active VMware network device |
| Total Active Hosts | 3 | Demonstrates network visibility |
| Topology | Successfully visualized | Helps understand network structure |

> These are network reconnaissance observations and are not confirmed vulnerabilities.

---

# 📈 Overall Findings

The three modules demonstrated different stages of cybersecurity reconnaissance.

### PM1 — External Footprinting

Information related to domain registration, web technologies, DNS, HTTP headers, WAF technology, and DNS infrastructure was identified.

### PM4 — OSINT

Publicly indexed email and host/subdomain information was identified using theHarvester.

### PM5 — Network Discovery

Three active hosts were identified within the local `10.0.0.0/24` network and visualized using Zenmap.

---

# ⚠️ Risk & Security Observations

The following observations were identified during the activities:

| Area | Observation | Potential Risk |
|---|---|---|
| Web Technology | Technologies and versions identifiable | Medium |
| WAF Detection | Defensive technology identifiable | Low |
| DNS Infrastructure | DNS/service information exposed | Medium |
| Public Email | Email information indexed | Medium |
| Public Subdomains | Multiple hosts identified | Medium |
| Network Hosts | Multiple active local hosts discovered | Medium |

> Risk ratings are based on reconnaissance observations and should not be interpreted as confirmed vulnerabilities.

---

# 🛡️ Recommendations

Based on the reconnaissance activities, the following general security recommendations are suggested:

### External Attack Surface

- Maintain an inventory of externally exposed assets.
- Regularly review DNS records and subdomains.
- Remove unnecessary public infrastructure information.
- Monitor external attack-surface exposure.

### Web Application

- Keep CMS and plugins updated.
- Review server information disclosure.
- Configure appropriate security headers.
- Regularly review WAF configuration.

### OSINT Exposure

- Review publicly indexed email addresses.
- Monitor search-engine indexing.
- Review publicly exposed subdomains.
- Avoid unnecessary disclosure of infrastructure information.

### Network Security

- Maintain an inventory of authorized devices.
- Segment networks where appropriate.
- Restrict unnecessary network access.
- Monitor unexpected devices.
- Regularly review network topology.
- Apply appropriate controls to virtualized environments.

---

# 🧠 Learning Outcomes

By completing these three modules, I gained practical experience in:

- Cybersecurity reconnaissance.
- Kali Linux footprinting.
- WHOIS enumeration.
- Web technology fingerprinting.
- DNS enumeration.
- HTTP header analysis.
- WAF detection.
- OSINT aggregation.
- Email and subdomain discovery.
- API-based OSINT limitations.
- Local network discovery.
- Nmap Ping Scanning.
- Zenmap usage.
- Network topology visualization.
- Security observation and risk documentation.
- Ethical and authorized security testing.

---

# 🔄 Complete Week 2 Workflow

```text
                    WEEK 2
                       │
           ┌───────────┴───────────┐
           │                       │
      PHASE 1                   PHASE 2
 Reconnaissance              Network Discovery
           │                       │
      ┌────┴────┐                  │
      │         │                  │
     PM1       PM4                PM5
      │         │                  │
 Kali Tools  theHarvester        Zenmap
      │         │                  │
      ↓         ↓                  ↓
 Footprinting  OSINT            Host Discovery
      │         │                  │
      ↓         ↓                  ↓
 Web/DNS     Email &            Active Hosts
 Information Subdomains             │
      │         │                  ↓
      └────┬────┘              Topology
           │
           └───────────┬───────────┘
                       ↓
                Security Analysis
                       ↓
                  Documentation
```

---

# 📸 Evidence Summary

## PM1 — Kali Linux Footprinting

```text
01-whois.png
02-whatweb.png
03-nslookup.png
04-curl.png
05-wafw00f.png
06-dnsrecon.png
```

## PM4 — theHarvester

```text
01-theharvester-help.png
02-theharvester-baidu-results.png
03-theharvester-api-sources.png
```

## PM5 — Zenmap

```text
01-zenmap-ping-scan.png
02-zenmap-network-topology.png
```

---

# 📁 Repository Structure

```text
W2 PM-FINAL - Report/
│
├── README.md
│
├── Letter of Authorization.pdf
│
├── W2 PM1 - Kali Linux Footprinting/
│   ├── README.md
│   ├── 01-whois.png
│   ├── 02-whatweb.png
│   ├── 03-nslookup.png
│   ├── 04-curl.png
│   ├── 05-wafw00f.png
│   └── 06-dnsrecon.png
│
├── W2 PM4 - theHarvester OSINT/
│   ├── README.md
│   ├── 01-theharvester-help.png
│   ├── 02-theharvester-baidu-results.png
│   └── 03-theharvester-api-sources.png
│
└── W2 PM5 - Zenmap Local Network Scanning/
    ├── README.md
    ├── 01-zenmap-ping-scan.png
    └── 02-zenmap-network-topology.png
```

---

# 📄 Letter of Authorization

An authorization letter is included with this final report to document the permitted scope of the cybersecurity activities.

### Authorization Document

[📄 View Letter of Authorization](Letter%20of%20Authorization.pdf)

The authorization document should be reviewed to ensure that all tested domains, systems, and networks are within the approved scope.

---

# 📋 Module Completion Summary

| Module | Activity | Main Tools | Status |
|---|---|---|---|
| PM1 | Kali Linux Footprinting | WHOIS, WhatWeb, Nslookup, cURL, WAFW00F, DNSRecon | ✅ Completed |
| PM4 | OSINT Aggregation | theHarvester | ✅ Completed |
| PM5 | Local Network Scanning | Zenmap / Nmap | ✅ Completed |

---

# ⚖️ Legal & Ethical Disclaimer

All cybersecurity activities documented in this report were performed for **educational and authorized cybersecurity training purposes**.

Testing should only be performed against systems, domains, and networks for which proper authorization has been obtained.

No unauthorized access, exploitation, or disruption should be performed.

Reconnaissance findings documented in this report represent observations collected during the exercises and should not automatically be considered confirmed security vulnerabilities.

The attached **Letter of Authorization** should be treated as the authoritative reference for the permitted scope of testing.

---

# 📌 Project Information

**Program:** Networkwalks Cybersecurity Internship  
**Batch:** B083  
**Week:** 2  
**Project:** Cybersecurity Reconnaissance & Network Scanning  
**Modules Completed:** PM1, PM4, PM5  
**Phases:** Phase 1 & Phase 2

---

# 👨‍💻 Author

**Gopal Mahajan**

Cybersecurity Student | VAPT & SOC Enthusiast

---

# 🙏 Acknowledgement

I would like to thank **Networkwalks** for providing this practical cybersecurity internship and the opportunity to gain hands-on experience with reconnaissance, OSINT, footprinting, network discovery, and security assessment tools.

---

# ✅ Final Completion

## Week 2 Project — Completed

The three selected modules were successfully completed:

```text
PM1 — Kali Linux Footprinting       ✅
PM4 — theHarvester OSINT            ✅
PM5 — Zenmap Network Scanning       ✅
```

**Overall Week 2 Project: COMPLETED ✅**
