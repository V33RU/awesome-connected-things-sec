# Industrial Control Systems (ICS) Security - Complete Guide

Industrial Control Systems (ICS) are the backbone of critical infrastructure: power, water, oil & gas, manufacturing, and more. This file covers the full ICS security landscape - basics, threats, exploits, major incidents, key vulnerabilities, standards, and the best resources.

---

## Table of Contents

- [Overview](#overview)
- [Key ICS Components](#key-ics-components)
- [Current ICS Security Challenges](#current-ics-security-challenges)
- [Attack Vectors & Notable Exploits](#attack-vectors--notable-exploits)
- [Critical ICS Vulnerabilities (2024–2025)](#critical-ics-vulnerabilities-20242025)
- [Infamous ICS-Focused Malware](#infamous-ics-focused-malware)
- [Ransomware & Targeted OT Attacks](#ransomware--targeted-ot-attacks)
- [ICS Security Best Practices & Standards](#ics-security-best-practices--standards)
- [Recent Research & Conference Insights](#recent-research--conference-insights)
- [Ultimate ICS Security Resources (Links)](#ultimate-ics-security-resources-links)

---

## Overview

Industrial Control Systems like SCADA, DCS, and PLCs—control everything from electricity generation to water treatment to factory automation. ICS environments:
- Run on legacy tech with safety & uptime as priorities.
- Are rapidly connecting to IT and cloud, exposing new risks.
> **A single breach may mean physical destruction, blackouts, or threats to human life.**  
Learn more: [ICS Overview by CISA](https://www.cisa.gov/topics/industrial-control-systems)

---

## Key ICS Components

- **SCADA** ([Supervisory Control and Data Acquisition](https://en.wikipedia.org/wiki/SCADA))
- **DCS** ([Distributed Control System](https://en.wikipedia.org/wiki/Distributed_control_system))
- **PLC** ([Programmable Logic Controllers](https://en.wikipedia.org/wiki/Programmable_logic_controller))
- **HMI** ([Human Machine Interface](https://en.wikipedia.org/wiki/Human–machine_interface))
- **RTU** ([Remote Terminal Unit](https://en.wikipedia.org/wiki/Remote_terminal_unit))
- **Industrial Protocols:** [Modbus](https://en.wikipedia.org/wiki/Modbus), [DNP3](https://en.wikipedia.org/wiki/DNP3), [OPC UA](https://opcfoundation.org/about/opc-technologies/opc-ua/), [Siemens S7](https://en.wikipedia.org/wiki/SIMATIC_S7), [Profibus](https://en.wikipedia.org/wiki/Profibus)

---

## Current ICS Security Challenges

- **Legacy Devices:** No modern authentication/encryption; many default credentials  
- **Maximum Availability:** Downtime is unacceptable, so patching is hard  
- **Insecure Protocols:** Industrial protocols lack security by design  
- **IT/OT Integration:** Merging IT & OT expands attack surface  
- **Human Factors:** Misconfiguration, lack of training, accidental insider error  
- **Supply Chain Risks:** 3rd-party software/equipment often introduce vulnerabilities  
- **Internet Exposure:** 100,000+ ICS devices found online in 2024 ([Shodan ICS Exposures](https://www.shodan.io/search?query=tags%3Aics))

[Rockwell Automation: What is ICS Security?](https://www.rockwellautomation.com/en-in/company/news/blogs/what-is-ics-security.html)

---

## Attack Vectors & Notable Exploits

| Incident                                              | Year   | Description/Impact                                                                              | Link                                                     |
|-------------------------------------------------------|--------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------|
| **Stuxnet**                                           | 2010   | Sabotaged Iran’s nuclear centrifuges via Siemens PLCs                                          | [Stuxnet WIRED](https://www.wired.com/2014/11/countdown-to-zero-day-stuxnet/)                  |
| **Maroochy Water Breach**                             | 2000   | Insider hacks sewage treatment SCADA to release sewage                                         | [SANS Report](https://www.sans.org/white-papers/901/)                                         |
| **Ukraine Power Grid Attack**                         | 2015   | Malware disables power for 200,000+ residents                                                  | [Dragos Blog](https://www.dragos.com/blog/industry-news/industroyer2/)                         |
| **Triton/Trisis**                                     | 2017   | Targeted Schneider Triconex SIS, aiming for sabotage                                           | [Dragos Triton](https://www.dragos.com/blog/industry-news/trisis-malware/)                     |
| **Colonial Pipeline Ransomware**                      | 2021   | Ransomware forces major East US fuel pipeline shutdown                                         | [CISA Response](https://www.cisa.gov/news-events/news/colonial-pipeline-incident-response)      |
| **Ransomhub (Spain, SCADA ransomware)**               | 2024   | Locks out bioenergy SCADA, encrypts 400+GB, disrupts ops                                      | [Cyble Report](https://cyble.com/blog/spanish-bioenergy-company-scada-system-attack/)           |
| **Fuxnet, FrostyGoop**                                | 2024–5 | Fuxnet (Russia gas/water sensor disruption), FrostyGoop (Ukraine heating sabotage)             | [Dragos 2024 Threats](https://www.dragos.com/knowledge-center/)                                |
| **US/UK/Global Water Utility PLC Hacks**              | 2023–4 | Iran-affiliated and hacktivist groups target exposed PLCs BLAM, causing real outages           | [Aon OT Report](https://www.aon.com/en/insights/cyber-labs/unveiling-the-dark-side-common-attacks-and-vulnerabilities-in-industrial-control-systems) |

- **Shodan Scan:** [Live Exposed ICS Devices](https://www.shodan.io/search?query=tags%3Aics)

---

## Critical ICS Vulnerabilities (2024–2025)

| Vendor          | Product(s)                       | CVE/Advisory                        | Impact                        | Link                                                                 |
|-----------------|----------------------------------|-------------------------------------|-------------------------------|----------------------------------------------------------------------|
| Siemens         | TeleControl Server Basic SQL     | CVE-2025-40312/-40313               | SQLi, remote access           | [Siemens Adv.](https://cert-portal.siemens.com/productcert/html/ssa-530408.html) |
| Siemens         | Industrial Edge Management       | CVE-2024-45032 (CVSS 10)            | Remote code exec, unauth      | [Cyble Analysis](https://cyble.com/blog/top-ics-vulnerabilities-this-week-19-september-2024/)   |
| Schneider Elec. | Modicon M580 PLCs                | ICSA-25-035-04                      | Remote code exec, persistence | [CISA Advisory](https://www.cisa.gov/news-events/cybersecurity-advisories/icsa-25-035-04)        |
| ABB             | MV Drives                        | ICSA-25-112-04                      | Privilege escalation          | [CISA Advisory](https://www.cisa.gov/news-events/cybersecurity-advisories/icsa-25-112-04)        |
| Viessmann       | Vitogate 300 Climate Controller  | Public PoC                          | Internet-exposed, RCE         | [Cyble Analysis](https://cyble.com/blog/top-ics-vulnerabilities-this-week-19-september-2024/)    |
| Schneider Elec. | Wiser Home WHC-5918A             | ICSA-25-112-03                      | Unauth remote control         | [CISA Advisory](https://www.cisa.gov/news-events/cybersecurity-advisories/icsa-25-112-03)        |

- Constantly updated: [ICS-CERT Vulnerabilities Feed](https://www.cisa.gov/news-events/cybersecurity-advisories?field_advisory_type_target_id=59136)

---

## Infamous ICS-Focused Malware

- **[Stuxnet](https://en.wikipedia.org/wiki/Stuxnet):** Destroyed centrifuges by reprogramming Siemens PLCs.
- **[Triton/Trisis](https://www.dragos.com/blog/industry-news/trisis-malware/):** Sabotaged safety instrumented systems in petrochemical plants.
- **[Industroyer/CrashOverride](https://www.welivesecurity.com/en/eset-research/crashoverride-malware/):** Ukraine power grid malware (uses ICS protocols directly).
- **[EKANS/Snake Ransomware](https://www.dragos.com/blog/industry-news/ekans-ransomware-and-ics-operations/):** Ransomware with ICS service/process termination.
- **[INCONTROLLER](https://www.mandiant.com/resources/blog/new-state-sponsored-threat-activity-incontroller):** Modular, state-sponsored toolkit for Omron/Schneider PLCs.
- **[Fuxnet & FrostyGoop](https://www.dragos.com/knowledge-center/):** Latest 2024–2025 ICS malware—sensor and process disruption.

---

## Ransomware & Targeted OT Attacks

- **Ransomware up 46% in 2025:** [Honeywell 2025 OT Threat Report](https://industrialcyber.co/reports/new-honeywell-2025-cyber-threat-report-reveals-ransomware-surges-46-percent-with-ot-systems-as-key-targets/)
- **Groups:** Cl0p, Ransomhub, and others are increasingly OT-aware.
- **Attack vectors:**  
   - USB devices: [Proofpoint 2024 Report](https://www.proofpoint.com/us/blog/threat-insight/usb-borne-attacks-increase)  
   - Ransomware-as-a-service (RaaS)  
   - Supply chain compromise, IABs (Initial Access Brokers)

[Dragos 2024 YIR Report](https://www.dragos.com/year-in-review/)

---

## ICS Security Best Practices & Standards

- **Segment OT/ICS from IT:** Air gaps, VLANs, strict firewalling  
- **Remove or restrict legacy protocols** (no Telnet/FTP)  
- **No default passwords!** Strong authentication for all ICS assets  
- **Periodic assessment & managed patching** (track vendor advisories)  
- **Asset inventory & network monitoring** — baseline normal, detect anomalies  
- **Multi-factor authentication (MFA), VPN for remote**  
- **Physical controls:** Limit physical access to ICS  
- **Incident response plans and backup recovery processes**
- **Security training for all OT/engineering staff**
- **Compliance standards:**  
   - [NIST SP 800-82 Guide to ICS Security](https://csrc.nist.gov/publications/detail/sp/800-82/rev-2/final)  
   - [ISA/IEC 62443 Overview](https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards)  
   - [ANSI/ISA 99](https://www.isa.org/standards-and-publications/isa-standards/isa99)

[Comprehensive ICS Security Practices — Vumetric](https://www.vumetric.com/blog/ics-security-best-practices/)

---

## Recent Research & Conference Insights

- **Geopolitics:** Ukraine war and US-China tensions fueling ICS attacks ([JPCERT 2025](https://blogs.jpcert.or.jp/en/2025/04/ics-conference2025.html))
- **Manufacturing:** 2/3 of ICS ransomware victims are manufacturing orgs ([Dragos 2024](https://www.dragos.com/knowledge-center/), [Honeywell 2025](https://industrialcyber.co/reports/new-honeywell-2025-cyber-threat-report-reveals-ransomware-surges-46-percent-with-ot-systems-as-key-targets/))
- **Disclosure:** SEC Form 8-K and new [CISA reporting rule](https://www.cisa.gov/resources-tools/directives/binding-operational-directive-22-01/) improving transparency.
- **Malware:** Repurposed older malware now dominates—little truly “new” malware, but attacks are more creative and critical.

---

## Ultimate ICS Security Resources (Links)

- [CISA: ICS/SCADA Security Hub](https://www.cisa.gov/topics/industrial-control-systems)
- [CISA ICS Advisories / Real-Time Vulnerabilities](https://www.cisa.gov/news-events/cybersecurity-advisories?field_advisory_type_target_id=59136)
- [Dragos ICS Threat Reports & YIR](https://www.dragos.com/knowledge-center/)
- [Honeywell OT Threat Report 2025](https://industrialcyber.co/reports/new-honeywell-2025-cyber-threat-report-reveals-ransomware-surges-46-percent-with-ot-systems-as-key-targets/)
- [Cyble: Weekly ICS Vulnerabilities](https://cyble.com/blog/top-ics-vulnerabilities-this-week-19-september-2024/)
- [Aon: Common Attacks and Vulnerabilities in ICS](https://www.aon.com/en/insights/cyber-labs/unveiling-the-dark-side-common-attacks-and-vulnerabilities-in-industrial-control-systems)
- [Rockwell: What is ICS Security?](https://www.rockwellautomation.com/en-in/company/news/blogs/what-is-ics-security.html)
- [Vumetric: ICS Security Best Practices](https://www.vumetric.com/blog/ics-security-best-practices/)
- [NIST SP 800-82 (ICS Security Standard)](https://csrc.nist.gov/publications/detail/sp/800-82/rev-2/final)
- [ISA/IEC 62443 Standard Series](https://www.isa.org/standards-and-publications/isa-standards/isa-iec-62443-series-of-standards)
- [SANS ICS Whitepapers](https://www.sans.org/white-papers/?cat=Industrial%20Control%20Systems)
- [JPCERT/CC ICS Security Conference Insights](https://blogs.jpcert.or.jp/en/2025/04/ics-conference2025.html)
- [Proofpoint: USB-Borne Attack Trends](https://www.proofpoint.com/us/blog/threat-insight/usb-borne-attacks-increase)
- [Check Point: ICS Security Hub](https://www.checkpoint.com/cyber-hub/network-security/what-is-industrial-control-systems-ics-security/)

---

> _This guide integrates case studies, threat intelligence, high-impact malware, critical vulnerabilities, and best practices, your single reference for research, defense, or investigation in ICS environments._

