# Robotics & ROS Security - Complete Guide

Modern robots run on the **Robot Operating System (ROS / ROS 2)** and a stack of DDS, embedded Linux, real-time controllers, perception ML models, and industrial fieldbuses. They blur the line between IT, OT, and AI — and they move in the physical world. This file covers the full robotics security landscape: ROS internals, attack surface, pentesting tools, checklists, known CVEs, frameworks, and the best community resources.

---

## Table of Contents

- [Overview](#overview)
- [Robot Security Attack Surface](#robot-security-attack-surface)
- [ROS 1 vs ROS 2 Security Model](#ros-1-vs-ros-2-security-model)
- [Pentesting Tools for Robots & ROS](#pentesting-tools-for-robots--ros)
- [Robot Pentesting Checklists](#robot-pentesting-checklists)
- [Known CVEs & Robot Vulnerabilities](#known-cves--robot-vulnerabilities)
- [Notable Robot Security Incidents & Research](#notable-robot-security-incidents--research)
- [AI / Perception Layer Attacks](#ai--perception-layer-attacks)
- [Industrial Robot Specifics](#industrial-robot-specifics)
- [Standards, Frameworks & Hardening](#standards-frameworks--hardening)
- [Research Papers](#research-papers)
- [Communities & Disclosure](#communities--disclosure)
- [Ultimate Robotics Security Resources](#ultimate-robotics-security-resources)

---

## Overview

A robot is a cyber-physical system: a network of nodes exchanging sensor and actuation messages over a middleware (ROS, DDS, or vendor-proprietary), running on an embedded OS, often connected to a cloud fleet manager and/or an industrial network.

> **A robot compromise is not just data theft — it can crash drones, derail mobile robots into people, or weld where there shouldn't be a weld.**

Key facts:
- **ROS** is the de-facto open-source robotics middleware, maintained by [Open Robotics](https://www.openrobotics.org/).
- **ROS 1** was designed without security in mind. It's plaintext, unauthenticated, and trivial to attack on a flat network.
- **ROS 2** uses **DDS (Data Distribution Service)** as transport. Security is *optional* via the **DDS-Security** spec, exposed in ROS 2 as **[SROS2](https://github.com/ros2/sros2)**.
- The **[Robot Vulnerability Database (RVD)](https://github.com/aliasrobotics/RVD)** is the largest robot-specific flaw registry (280+ flaws, 236 ROS 2 weaknesses), maintained by [Alias Robotics](https://aliasrobotics.com/).

Learn more:
- [ROS.org — official site](https://www.ros.org/)
- [ROS 2 Security Working Group](https://github.com/ros-security/community)
- [Alias Robotics — Robot Cybersecurity](https://aliasrobotics.com/)

---

## Robot Security Attack Surface

| Layer | Components | Typical Weaknesses |
|---|---|---|
| **Hardware** | JTAG, UART, USB, SD, CAN, EtherCAT, I²C, SPI | Exposed debug ports, glitching, sensor spoofing |
| **Firmware / OS** | Embedded Linux (Ubuntu, Yocto), RTOS, bootloader | Default creds, world-writable files, missing secure boot |
| **Middleware** | ROS 1 master, ROS 2 / DDS, MQTT, ZeroMQ | No auth (ROS 1), DDS misconfig, plaintext topics |
| **Application** | ROS nodes, services, parameter server, `.launch`/`.yaml` | Param poisoning, node spoofing, deserialization bugs |
| **Perception / AI** | LiDAR, RGB/RGBD cameras, IMU, ML models | Adversarial inputs, sensor spoofing, model tampering |
| **Network** | Wi-Fi, 4G/5G, Ethernet, Bluetooth | Open services, weak Wi-Fi, no segmentation from IT/OT |
| **Cloud / Fleet** | Vendor cloud, web dashboards, REST/MQTT bridges | OWASP Top 10, weak API auth, exposed endpoints |
| **Physical / Safety** | E-stops, safety PLCs, motor controllers | Bypassable safety logic, unsafe defaults |

---

## ROS 1 vs ROS 2 Security Model

### ROS 1 — Insecure by Design
- Central **ROS Master** on TCP **11311** (XML-RPC).
- **No authentication.** Any node on the network can register, subscribe, publish, or de-register others.
- **No encryption.** Everything is plaintext over TCPROS/UDPROS.
- **XML-RPC injection** and **node hijacking** are trivial.
- Mitigations are network-layer only: VPN, VLAN segmentation, IPsec.

### ROS 2 — Security Optional via SROS2 / DDS-Security
- Uses **DDS** (RTPS) — distributed, no master.
- **DDS Security** plugins (Authentication, Access Control, Cryptographic) provide PKI-based identity, signed permissions, AES-GCM encryption.
- Exposed in ROS 2 as **[SROS2](https://github.com/ros2/sros2)** CLI tooling: `ros2 security create_keystore`, `create_enclave`, etc.
- **Common failures**: SROS2 disabled in dev/prod, wrong `ROS_DOMAIN_ID`, missing access control policies, permissive `governance.xml`.
- Reference: [SROS2 docs](https://docs.ros.org/en/rolling/Tutorials/Advanced/Security/Introducing-ros2-security.html), [DDS Security spec (OMG)](https://www.omg.org/spec/DDS-SECURITY/).

---

## Pentesting Tools for Robots & ROS

### ROS-Specific
| Tool | Purpose | Link |
|---|---|---|
| **ROSPenTo** | XML-RPC pentest tool for ROS Master & nodes — enumerates and manipulates the ROS graph | [github.com/jr-robotics/ROSPenTo](https://github.com/jr-robotics/ROSPenTo) |
| **ROSploit** | Two-phase recon + exploit framework for ROS 1 | [github.com/seanrivera/rosploit](https://github.com/seanrivera/rosploit) |
| **roschaos** | Chaos engineering / fault injection across the ROS graph | [github.com/ruffsl/roschaos](https://github.com/ruffsl/roschaos) |
| **Robosploit (Alurity)** | Robotics exploitation framework by Alias Robotics | [aliasrobotics.com/alurity.php](https://aliasrobotics.com/alurity.php) |
| **HAROS** | Static analysis framework for ROS C++/Python codebases | [github.com/git-afsantos/haros](https://github.com/git-afsantos/haros) |
| **rosmap** | Auto-discovers ROS Master endpoints | [github.com/aliasrobotics/aztarna](https://github.com/aliasrobotics/aztarna) |
| **aztarna** | Footprinting tool for ROS, SROS, industrial routers | [github.com/aliasrobotics/aztarna](https://github.com/aliasrobotics/aztarna) |
| **RVDP** | Robot Vulnerability Database CLI | [github.com/aliasrobotics/RVD](https://github.com/aliasrobotics/RVD) |
| **RSF (Robot Security Framework)** | Methodology + tooling for robot assessments | [github.com/aliasrobotics/RSF](https://github.com/aliasrobotics/RSF) |

### Exploitation Frameworks
- **[Metasploit Framework](https://github.com/rapid7/metasploit-framework)** — general; a few ICS/robot modules.
- **[ISF — Industrial Security Exploitation Framework](https://github.com/dark-lbp/isf)** — ICS/robotics modules.
- **[RouterSploit](https://github.com/threat9/routersploit)** — embedded device exploits, useful for robot controllers.
- **[w3af](https://github.com/andresriancho/w3af)** — for robot web dashboards.

### Network / DDS Analysis
- **[Nmap](https://nmap.org/)** — service discovery; ports 11311 (ROS 1), 7400-7500 (DDS RTPS).
- **[Wireshark](https://www.wireshark.org/)** with the [RTPS dissector](https://wiki.wireshark.org/Protocols/rtps) — DDS traffic inspection.
- **[Scapy](https://scapy.net/)** — packet crafting for RTPS / TCPROS.
- **[SSLyze](https://github.com/nabla-c0d3/sslyze)** — for robot HTTPS endpoints.
- **[fastdds-discovery-server](https://fast-dds.docs.eprosima.com/en/latest/)** — DDS discovery analysis.

### Hardware Pentesting
- **[Bus Pirate](http://dangerousprototypes.com/docs/Bus_Pirate)**, **[JTAGulator](http://www.grandideastudio.com/jtagulator/)**, **[Saleae](https://www.saleae.com/)** — physical bus probing.
- **[ChipWhisperer](https://www.newae.com/chipwhisperer)** — side-channel + glitching of robot MCUs.
- **[CANalyse](https://github.com/KuKuXia/CANalyse)** / **[caringcaribou](https://github.com/CaringCaribou/caringcaribou)** — CAN/CANopen on industrial arms.
- **[Flipper Zero](https://flipperzero.one/)** — RF/sub-GHz on tele-op links.

### Static & SBOM
- **[Flawfinder](https://dwheeler.com/flawfinder/)**, **[RATS](https://github.com/andrew-d/rough-auditing-tool-for-security)**, **[Cppcheck](http://cppcheck.sourceforge.net/)** — C/C++ source scanners.
- **[SonarQube](https://www.sonarqube.org/)**, **[Semgrep](https://semgrep.dev/)** — SAST.
- **[OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/)**, **[Syft + Grype](https://github.com/anchore/grype)** — SBOM + CVE matching for ROS dependencies.

### Fuzzing
- **[AFL++](https://github.com/AFLplusplus/AFLplusplus)**, **[libFuzzer](https://llvm.org/docs/LibFuzzer.html)** — message parser fuzzing.
- **[Boofuzz](https://github.com/jtpereyda/boofuzz)** — protocol fuzzing for ROS messages and DDS RTPS.
- **[Google Sanitizers](https://github.com/google/sanitizers)** — ASan/UBSan/TSan for ROS nodes.

---

## Robot Pentesting Checklists

### 1. Network & ROS Graph
- [ ] Identify ROS version (ROS 1 vs ROS 2) and middleware (Fast-DDS, Cyclone, RTI Connext).
- [ ] Scan for ROS Master XML-RPC on **TCP 11311**.
- [ ] Enumerate **all topics, services, parameters**: `rostopic list`, `rosservice list`, `rosparam list`.
- [ ] List active nodes and inspect their connections: `rosnode list` / `rosnode info`.
- [ ] For ROS 2: probe RTPS discovery on UDP **7400-7500**; enumerate participants with `ros2 node list`, `ros2 topic list`.
- [ ] Check `ROS_DOMAIN_ID` segregation and cross-domain leakage.
- [ ] Verify whether **SROS2 / DDS-Security** is enabled and policies (governance/permissions XML) are signed.
- [ ] Attempt **node spoofing**: register a malicious node with the Master and intercept topics.
- [ ] Attempt **topic poisoning**: publish on safety-critical topics (`/cmd_vel`, `/joint_states`).
- [ ] Test **MITM** on TCPROS / RTPS where no encryption is enforced.

### 2. Hardware
- [ ] Identify and probe **JTAG, SWD, UART, USB-OTG, SD card** interfaces.
- [ ] Attempt firmware dump via debug interface or SPI flash readout.
- [ ] Probe **CAN / CANopen / EtherCAT** buses for unauthenticated motion commands.
- [ ] Inspect **I²C / SPI** sensor lines for tamper / spoofing potential.
- [ ] Check for **secure boot**, signed firmware, and TPM/secure-element presence.

### 3. Firmware & OS
- [ ] Fingerprint OS (Ubuntu, Yocto, ROS distro).
- [ ] Test for **default or hardcoded credentials** (vendor, SSH, web UI).
- [ ] Look for SUID binaries, world-writable dirs, lax sudoers (CWE-276).
- [ ] Check for **outdated apt/pip/rosdep packages** with known CVEs.
- [ ] Verify SBOM exists and is current; run [Syft](https://github.com/anchore/syft) + [Grype](https://github.com/anchore/grype).
- [ ] Test for **race conditions** in init scripts (CWE-362).
- [ ] Inspect `/etc/ros/`, `~/.ros/`, and launch files for hardcoded secrets.

### 4. Application & ROS Graph (Logic)
- [ ] **Parameter server poisoning** — read/write sensitive params (`/rosparam`).
- [ ] **Launch file injection** — substitute `.launch` / `.yaml` to load attacker nodes.
- [ ] **Deserialization** — fuzz custom `.msg` parsers (esp. user-defined types).
- [ ] **DoS** — topic flooding, parameter storms, RTPS announcement spam.
- [ ] **Service abuse** — enumerate `rosservice` endpoints for unauthenticated command exec, e-stop bypass, motion override.
- [ ] Check for **command injection** in service handlers shelling out (`os.system`, `subprocess`).

### 5. Auth, Access Control & Web
- [ ] Verify ROS 1 deployment is on an **isolated, segmented** network.
- [ ] Confirm SROS2 enclaves are scoped to least privilege.
- [ ] Robot **web dashboard / REST / WebSocket bridge (`rosbridge_suite`)** — apply OWASP Top 10 (authN/Z, CSRF, IDOR, SSRF).
- [ ] Test **rosbridge** WebSocket on port **9090** for unauthenticated topic publishing.
- [ ] Check TLS hygiene on every HTTPS/MQTT endpoint.

### 6. AI / Perception
- [ ] Inventory perception models (object detection, SLAM, voice).
- [ ] Test **adversarial robustness** of camera/LiDAR pipelines.
- [ ] Verify model file integrity (signatures, hashes) on disk.
- [ ] Check for unprotected model update / OTA channels.

---

## Known CVEs & Robot Vulnerabilities

### ROS 1 Core
| ID | Description | Reference |
|---|---|---|
| **RVD#87** | Lack of authentication in ROS computational graph — node impersonation & topic hijack | [RVD#87](https://github.com/aliasrobotics/RVD/issues/87) |
| **RVD#88** | Lack of encryption in ROS comms — plaintext sniffing of all topics | [RVD#88](https://github.com/aliasrobotics/RVD/issues/88) |
| **CVE-2019-13445** | ROS `ros_comm` denial-of-service via crafted XMLRPC | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2019-13445) |

### ROS 2 / Nav2 / DDS
| ID | Component | Description | Reference |
|---|---|---|---|
| **CVE-2024-37861** | `nav2_amcl` (Nav2 Humble) | Buffer overflow via crafted `.yaml` triggering RCE | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2024-37861) |
| **CVE-2024-41648** | `navigation2` (Humble) | Insecure file permissions enable arbitrary code execution | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2024-41648) |
| **CVE-2022-30262 ... 30276** | eProsima Fast-DDS, RTI Connext, OpenDDS | Series of DDS RTPS implementation bugs (parsing, DoS, memory) | [Alias Robotics DDS](https://news.aliasrobotics.com/alias-robotics-dds-ros2-vulnerabilities/) |

### MiR Industrial Mobile Robots
| ID | Description | Reference |
|---|---|---|
| **CVE-2020-10264 ... 10280** | Bundle of MiR controller flaws: insecure Ubuntu defaults, race conditions (CWE-362), permission errors (CWE-276), default creds, exposed services | [CVE-2020-10279](https://nvd.nist.gov/vuln/detail/CVE-2020-10279) |

### Universal Robots (UR3 / UR5 / UR10)
| ID | Description | Reference |
|---|---|---|
| **CVE-2020-10266** | Insecure default settings on UR controllers | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2020-10266) |
| **CVE-2020-10290** | Unauthenticated remote code execution on UR endpoint — used in red-team chains to fully compromise ROS network | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2020-10290) |
| **CVE-2020-10291 / 10292** | Missing authentication & weak crypto on URCaps/Modbus interfaces | [Alias UR study](https://aliasrobotics.com/case-study-red-teaming.php) |
| **RVD#1495** | UR robot endpoint code execution, ROS pivot | [RVD](https://github.com/aliasrobotics/RVD) |

### ABB Industrial Robots
| ID | Description | Reference |
|---|---|---|
| **CVE-2020-10281 ... 10287** | ABB controller / RobotWare flaws — missing auth, weak protocols, control parameter tampering | [Alias CNA](https://news.aliasrobotics.com/alias-robotics-as-cna-from-research-to-robotics-user-empowerment/) |

### Softbank NAO / Pepper Social Robots
| ID | Description | Reference |
|---|---|---|
| **CVE-2020-10268, 10275 ... 10289** | NAOqi services exposed without authentication; remote takeover of social robots | [Alias CNA](https://news.aliasrobotics.com/alias-robotics-as-cna-from-research-to-robotics-user-empowerment/) |

### Other Notables
- **Trend Micro "Rogue Robots" (2017)** — first major paper showing how to tamper with control parameters, calibration, and safety logic on ABB/Kuka/Fanuc/Yaskawa. [Report](https://documents.trendmicro.com/assets/wp/wp-industrial-robot-security.pdf)
- **Boston Dynamics Spot — `rosbridge` exposure research** — see talks at DEF CON / Black Hat (2022-2024).
- **Tesla Optimus, Unitree G1/H1** — recent reverse engineering and firmware analysis efforts by independent researchers.

> 📚 **Authoritative registry:** [Robot Vulnerability Database (RVD)](https://github.com/aliasrobotics/RVD) — 280+ flaws, 236+ ROS 2 weaknesses.

---

## Notable Robot Security Incidents & Research

| Year | Incident / Paper | Summary | Link |
|---|---|---|---|
| 2017 | **Trend Micro — Rogue Robots** | First end-to-end attack chain on industrial arms (ABB, Kuka) | [Paper](https://documents.trendmicro.com/assets/wp/wp-industrial-robot-security.pdf) |
| 2018 | **IOActive — Hacking Robots Before Skynet** | 50+ flaws in NAO, Pepper, UR, Baxter | [IOActive](https://act-on.ioactive.com/acton/attachment/34793/f-484f0d52-37bc-4313-a8ee-fc8b659d4b06/1/-/-/-/-/Hacking-Robots-Before-Skynet-Paper_Final.pdf) |
| 2019 | **Alias Robotics — Robot Vulnerability Database launch** | First public robot CVE registry | [Discourse](https://discourse.openrobotics.org/t/introducing-the-robot-vulnerability-database/11105) |
| 2020 | **MiR / UR / ABB CVE wave** | Coordinated disclosure of dozens of robot CVEs | [Alias as CNA](https://news.aliasrobotics.com/alias-robotics-as-cna-from-research-to-robotics-user-empowerment/) |
| 2022 | **DDS RTPS bug class** | Series of CVEs across all major DDS vendors | [Alias DDS](https://news.aliasrobotics.com/alias-robotics-dds-ros2-vulnerabilities/) |
| 2024 | **Nav2 buffer overflow (CVE-2024-37861)** | First RCE in ROS 2 Nav stack via crafted YAML | [NVD](https://nvd.nist.gov/vuln/detail/CVE-2024-37861) |
| 2024-2025 | **Humanoid robot reversing** | Independent researchers reversing Unitree G1, Tesla Optimus firmware | (various talks) |

---

## AI / Perception Layer Attacks

Modern robots run ML for vision, planning, and dialog. New attack classes:

- **Adversarial examples** — physical-world patches that fool object detectors (e.g., stop-sign attacks on autonomous robots).
- **Sensor spoofing** — laser glare on LiDAR, ultrasonic injection on MEMS, GPS spoofing on outdoor robots.
- **Data poisoning** — manipulating training datasets for fleet-learned models.
- **Model integrity attacks** — tampering with on-device `.onnx` / `.pt` / `.engine` files; missing signatures.
- **Prompt injection on LLM-controlled robots** — emerging issue for VLA (Vision-Language-Action) models like RT-2, Figure-01 stack, OpenVLA.
- **Backdoored foundation models** — trojan triggers in pretrained vision/LLM backbones.

Reading:
- [Adversarial Robustness Toolbox (IBM)](https://github.com/Trusted-AI/adversarial-robustness-toolbox)
- [RoboPAIR — LLM-controlled robot jailbreaking (Penn, 2024)](https://robopair.org/)
- [LiDAR Spoofing Research — Cao et al.](https://arxiv.org/abs/1907.06826)

---

## Industrial Robot Specifics

- **Remote modification of control parameters / calibration** — tiny offsets cause defective parts or unsafe motion (Trend Micro).
- **Safety PLC bypass** — light curtains, e-stops, and safety zones controlled by separately certified safety PLCs; check whether they can be reached or overridden from the standard network.
- **Network pivot** — a compromised cell controller is often the bridge from IT to the deep OT network.
- **Vendor remote-access tools** (KUKA WorkVisual, ABB RobotStudio, Fanuc Roboguide) — historically weak auth, often exposed for "remote support".
- **Fieldbuses**: **EtherCAT**, **PROFINET**, **CANopen**, **EtherNet/IP** — typically unauthenticated; treat as inside the trust boundary.

Pivot reading: [ICS Security guide](../ICS/Industrial-Control-Systems.md) in this repo.

---

## Standards, Frameworks & Hardening

| Standard / Framework | Scope | Link |
|---|---|---|
| **ISO 10218-1/-2** | Industrial robot safety | [ISO 10218](https://www.iso.org/standard/73933.html) |
| **ISO/TS 15066** | Collaborative robots (cobots) safety | [ISO 15066](https://www.iso.org/standard/62996.html) |
| **IEC 62443** | Industrial automation & control systems security | [IEC 62443](https://www.iec.ch/blog/understanding-iec-62443) |
| **NIST SP 800-82 Rev.3** | Guide to OT security (covers robotics) | [NIST](https://csrc.nist.gov/pubs/sp/800/82/r3/final) |
| **MITRE ATT&CK for ICS** | TTPs applicable to industrial robots | [attack.mitre.org/matrices/ics](https://attack.mitre.org/matrices/ics/) |
| **SROS2 / DDS-Security** | Native ROS 2 security model | [SROS2](https://github.com/ros2/sros2) |
| **Robot Security Framework (RSF)** | Methodology for robot security assessments | [github.com/aliasrobotics/RSF](https://github.com/aliasrobotics/RSF) |
| **OWASP IoT Top 10** | Applies to robot web/cloud surfaces | [OWASP IoT](https://owasp.org/www-project-internet-of-things/) |
| **ENISA — Robotics** | EU agency guidance | [ENISA Robotics](https://www.enisa.europa.eu/) |

### Hardening Quick Wins
- Disable ROS 1 in production; if unavoidable, **air-gap or VPN-only**.
- Enable **SROS2** with signed governance / permissions XML.
- Pin a unique non-default `ROS_DOMAIN_ID` per deployment.
- Disable `rosbridge` or front it with auth + TLS.
- Secure boot + signed firmware; encrypted filesystem on removable media.
- Network segmentation: separate **safety**, **control**, **perception**, **cloud** VLANs.
- Continuous SBOM scanning ([Syft](https://github.com/anchore/syft) + [Grype](https://github.com/anchore/grype)).
- Subscribe to **[ROS Security Vulnerability Disclosures](https://ros.org/reps/rep-2006.html)** (REP-2006).

---

## Research Papers

- **[SROS2: Usable Cyber Security Tools for ROS 2](https://arxiv.org/abs/2208.02615)** — Mayoral-Vilches et al., 2022.
- **[Robot Vulnerability Database — A Public Robot Flaw Registry](https://arxiv.org/abs/1912.11299)** — Mayoral-Vilches et al., 2019.
- **[DevSecOps for Robotics](https://arxiv.org/abs/2003.10402)** — Mayoral-Vilches et al., 2020.
- **[Industrial Robot Security: A Survey](https://documents.trendmicro.com/assets/wp/wp-industrial-robot-security.pdf)** — Trend Micro / Politecnico di Milano, 2017.
- **[Hacking Robots Before Skynet](https://act-on.ioactive.com/acton/attachment/34793/f-484f0d52-37bc-4313-a8ee-fc8b659d4b06/1/-/-/-/-/Hacking-Robots-Before-Skynet-Paper_Final.pdf)** — Cerrudo & Apa, IOActive, 2018.
- **[RoboPAIR: Jailbreaking LLM-Controlled Robots](https://robopair.org/)** — UPenn, 2024.
- **[Penetration Testing ROS — IROS](https://arxiv.org/abs/1805.02333)** — Dieber et al., 2018.

---

## Communities & Disclosure

- **[ROS 2 Security Working Group](https://github.com/ros-security/community)** — official ROS security WG.
- **[Alias Robotics](https://aliasrobotics.com/)** — CNA for robot CVEs; runs RVD.
- **[IOTSRG](https://iotsrg.org/)** — IoT Security Research Group (this repo's home).
- **[ROS Discourse — Security category](https://discourse.openrobotics.org/c/security/)**.
- **[ICS-CERT / CISA](https://www.cisa.gov/topics/industrial-control-systems)** — for industrial robot advisories.
- **Disclosure**: report ROS bugs via [REP-2006](https://ros.org/reps/rep-2006.html); vendor robots via vendor PSIRT or Alias Robotics as CNA.

---

## Ultimate Robotics Security Resources

### Books
- *Robot Operating System (ROS) for Absolute Beginners* — Lentin Joseph.
- *Hands-On ROS for Robotics Programming* — Bernardo Ronquillo Japón.
- *Industrial Cybersecurity* — Pascal Ackerman (covers OT/robotics).

### Courses & Trainings
- [Cybersecurity for Robotics — Alias Robotics](https://aliasrobotics.com/training.php).
- [The Construct — ROS / ROS 2 Courses](https://www.theconstructsim.com/).
- [SANS ICS410 — ICS/SCADA Security Essentials](https://www.sans.org/cyber-security-courses/ics-scada-cyber-security-essentials/).

### CTFs & Labs
- **[Alurity](https://aliasrobotics.com/alurity.php)** — modular toolbox for robot cybersecurity labs.
- **[ROS-Industrial Training](https://github.com/ros-industrial/industrial_training)** — base for security lab builds.
- **[Gazebo](https://gazebosim.org/)** + custom red-team scenarios for safe robot exploitation practice.

### Newsletters / Blogs
- [Alias Robotics blog](https://news.aliasrobotics.com/).
- [ROS Discourse](https://discourse.openrobotics.org/).
- [Trend Micro Research — Robotics](https://www.trendmicro.com/vinfo/us/security/news/internet-of-things).
- [Fort Robotics blog](https://www.fortrobotics.com/news).

---

> 🤝 **Contribute:** PRs welcome — add CVEs, tools, write-ups, or new research. See [CONTRIBUTING.md](../../CONTRIBUTING.md).
>
> 🛡️ Maintained as part of [Awesome Connected Things Security](../../README.md) by [IOTSRG](https://iotsrg.org/).
