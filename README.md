# Week 2 – Footprinting & Network Scanning

**Networkwalks Cybersecurity Program · Batch B084 · Author: Abdulkadiri Adaranijo**
Report date: 10 November 2026 · Phases covered: **Reconnaissance & Footprinting** and **Scanning & Network Discovery**

This repository summarizes my Week 2 practical work: five modules covering passive and light-touch reconnaissance and a local network scan. The full write-up is in [`report/`](report/). Everything here is **education and research only**; no exploitation or vulnerability validation was performed.

> **Authorization & ethics.** `networkwalks.com` was tested under a written letter of authorization from Networkwalks. `microsoft.com` was a lab-designated public example (public sources only). The GHDB exercise involved passive viewing of publicly indexed pages (no logins, no control of devices, no downloads). The network scan was run on my own LAN. IP addresses, MAC suffixes, tokens and live camera imagery are masked throughout. See [Scope and ethics](#scope-and-ethics).

## Modules

| # | Module | Target | Date | Folder |
|---|--------|--------|------|--------|
| 1 | Footprinting with multiple Kali tools (WHOIS, WhatWeb, nslookup, curl, wafw00f, DNSRecon) | networkwalks.com | 8 Nov 2026 | [module-1](module-1-multiple-kali-tools/) |
| 2 | Footprinting with the Google Hacking Database (GHDB) | Public search results | 8 Nov 2026 | [module-2](module-2-ghdb/) |
| 3 | Footprinting with Maltego CE | networkwalks.com | 8 Nov 2026 | [module-3](module-3-maltego/) |
| 4 | Footprinting with theHarvester | microsoft.com (lab example) | 9 Nov 2026 | [module-4](module-4-theharvester/) |
| 5 | Network scanning with Zenmap | My own LAN (192.168.100.0/24) | 10 Nov 2026 | [module-5](module-5-zenmap/) |

## Key findings (13 observations: 1 High · 4 Medium · 5 Low · 3 Info)

| # | Finding | Module | Level |
|---|---------|--------|-------|
| 1 | Internet-exposed cameras reachable without authentication | 2 | High |
| 2 | Missing HTTP security headers; REST API and cache details exposed | 1 | Medium |
| 3 | SPF soft fail (`~all`) and DNSSEC unsigned | 1 | Medium |
| 4 | Indexed open directory listings | 2 | Medium |
| 5 | Infostealer-exposure statistics reported by a third-party source | 4 | Medium |
| 6 | Web technology and version disclosure (WordPress, plugin) | 1 | Low |
| 7 | DNS server version disclosure (BIND) | 1 | Low |
| 8 | Public role mailbox discoverable | 1, 3 | Low |
| 9 | Large passive attack surface of a public domain (lab example) | 4 | Low |
| 10 | Local hosts easily discoverable; one device with a randomized MAC | 5 | Low |
| 11 | Registration and hosting profile (privacy proxy and locks are good) | 1 | Info |
| 12 | WAF present and fingerprintable (ModSecurity) | 1 | Info |
| 13 | Reduced OSINT coverage without API keys | 4 | Info |

Most items are observations, not confirmed vulnerabilities. Findings 1 and 4 involved direct, unauthenticated access that was observed (viewing only).

## Top recommendations
1. Add HSTS, CSP, X-Frame-Options and X-Content-Type-Options; keep WordPress and plugins patched.
2. Move SPF to a hard fail, publish DKIM and an enforced DMARC policy, and enable DNSSEC where supported.
3. Never expose cameras directly to the internet: require authentication, use a VPN, update firmware.
4. Disable directory listing and regularly dork your own domains for accidental exposure.
5. Keep a DHCP-based device inventory, since randomized MACs defeat vendor lookup.

## Tools and versions
Kali Linux (VM) · WHOIS · WhatWeb · nslookup · curl · WAFW00F 2.4.2 · DNSRecon · Exploit-DB GHDB + Google · Maltego CE 4.13.0 · theHarvester 4.10.1 · Zenmap / Nmap 7.993 (Windows)

## Repository layout
```
report/                          Full report (DOCX and PDF)
module-1-multiple-kali-tools/    README + evidence/
module-2-ghdb/                   README + evidence/
module-3-maltego/                README + evidence/
module-4-theharvester/           README + evidence/ + results-summary.md
module-5-zenmap/                 README + evidence/
```

## Scope and ethics
- **Authorized:** networkwalks.com (written letter of authorization held by the author).
- **Lab-designated, passive only:** microsoft.com via public OSINT sources; public search results for GHDB.
- **Own network:** 192.168.100.0/24.
- **Not published here:** raw tool output, third-party host lists, camera links, and unmasked screenshots. Open directories are described generically and are not linked.

## Disclaimer
These materials are for education and research purposes only. Do not use anything here to break the law. The author, the instructor and Networkwalks are not responsible for what you do with this knowledge. Unauthorised access is a crime in most countries even when nothing is damaged.

## Author
**Abdulkadiri Adaranijo** – Cybersecurity Professional, B084
LinkedIn: <https://www.linkedin.com/in/tj-adaranijo-02183a191/>
