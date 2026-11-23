<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0b1020,50:3b82f6,100:22d3ee&height=230&section=header&text=Gonzalo%20Alegre&fontSize=58&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Cloud%20%26%20Security%20Analyst&descAlignY=60&descSize=20" alt="Gonzalo Alegre - Cloud and Security Analyst" width="100%">
</p>
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&duration=3000&pause=1000&color=22D3EE&center=true&vCenter=true&width=850&lines=I+detect+attacks+with+Suricata+%2B+Wazuh;I+document+each+case+like+a+real+SOC;I+build+serverless+infrastructure+on+AWS;I+analyze+traffic+and+forensic+evidence;Hardening+Active+Directory" alt="Typing animation: detection, SOC case documentation, AWS serverless, forensics, Active Directory hardening">
</p>
<p align="center">
  <a href="https://www.linkedin.com/in/alegregonzalos/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://github.com/AlegreGonza/soc-home-lab"><img src="https://img.shields.io/badge/SOC_Lab-111827?style=for-the-badge&logo=github&logoColor=white" alt="SOC Lab"></a>
  <a href="https://github.com/AlegreGonza/uptime-sentinel"><img src="https://img.shields.io/badge/uptime--sentinel-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white" alt="uptime-sentinel"></a>
  <a href="https://github.com/AlegreGonza/tracewell"><img src="https://img.shields.io/badge/Tracewell-22C55E?style=for-the-badge&logo=python&logoColor=white" alt="Tracewell"></a>
</p>
---
 
## About me
 
Cloud & Security Analyst based in Corrientes, Argentina. Information Systems student at UNNE, with more than two years of L2 support at an ISP. I work on Windows Server, Linux and internal systems, and I document every incident with its root cause.
 
I treat my projects as complete case studies: a self-hosted SOC lab where I build, operate and attack my own environment, and a serverless monitoring system on AWS deployed with Terraform. Every SOC lab incident is recorded as a case, the way a real SOC would do it.
 
## Current focus
 
- Self-hosted SOC lab (Suricata + Wazuh + TheHive): controlled attacks, documented end to end
- Detection engineering: Sigma rules, SOAR automation, MITRE ATT&CK mapping
- FortiGate firewalls, building on Fortinet NSE 1–3
- Incident response with SANS PICERL and NIST SP 800-61
## Featured projects
 
**[SOC Home Lab](https://github.com/AlegreGonza/soc-home-lab)** · in progress · 6 documented cases
 
Controlled attacks against my own machines, detected with Suricata (NIDS) and Wazuh (HIDS and FIM). Wazuh alerts open cases automatically in TheHive.
 
```
Attack → Detection (Suricata / Wazuh) → Case (TheHive) → PICERL report + MITRE ATT&CK → Rule tuning
```
 
| # | Case | MITRE ATT&CK |
|---|---|---|
| 01 | SSH brute force and data exfiltration | T1110.001 · T1048.002 |
| 02 | sudo abuse and credential dumping | T1003.008 · T1548.003 |
| 03 | Privilege escalation with GTFOBins | T1548.003 · T1059.004 |
| 04 | Active Response: automatic brute-force containment | T1110.001 |
| 05 | Active Directory: password spray → DCSync → Golden Ticket | T1003.006 · T1558.001 |
| 06 | LLMNR / NBT-NS / mDNS poisoning and NTLMv2 capture | T1557.001 |
 
- Wazuh rules validated with `wazuh-logtest`, written in Sigma first and converted to Wazuh syntax
- DCSync, Kerberoasting and Golden Ticket rules written and loaded; pending confirmation with real traffic
- Active Response (firewall-drop) limited to the attacker's IP, with automatic unblock
- Documented blind spots: commands run without sudo leave no trace; encrypted SSH/SCP hides content from the NIDS
**[Tracewell](https://github.com/AlegreGonza/tracewell)** · MVP
 
Desktop traffic analyzer for SOC Tier 1 triage. Reads `.pcap` / `.pcapng` files or captures live traffic.
 
```
Capture → Sessions (5-tuple) → YAML rules (MITRE) → Alerts with evidence → JSON export
```
 
- Streaming reads with constant memory, bidirectional sessions, filters by protocol, IP and port, per-packet hexdump
- YAML rules mapped to MITRE ATT&CK: port scanning (T1046), cleartext FTP credentials (T1040), suspicious DNS by entropy (T1071.004)
- Configurable trusted-domain list to reduce false positives; passwords are never stored
- Security: API bound to `127.0.0.1`, cross-origin protection, strict input validation, no user paths in errors
- Stack: Python, FastAPI, React, Scapy, dpkt, pywebview · pytest, Vitest, mypy
**[uptime-sentinel](https://github.com/AlegreGonza/uptime-sentinel)** · published · MIT
 
Serverless availability monitor on AWS, defined in Terraform. Checks sites every 5 minutes, stores history in DynamoDB and sends email alerts.
 
```
EventBridge (5 min) → Monitor Lambda → Checker Lambda → DynamoDB (history) → SNS (email)
```
 
- State-transition alerts: pre-alert on first failure, downtime alert after 3 consecutive failures, recovery notice; no repeats while the site stays down
- 0–100 risk index comparing recent checks against the baseline
- CloudWatch alarm if the monitor itself stops running
- API Gateway protected by API key, plus a Python CLI
- SSRF controls: HTTPS only, DNS validation, non-public addresses rejected, connection pinned to the validated IP
- 141 unit tests; Gitleaks and Checkov run on every push
- Presented at NicaHackFest 2026
**[ad-hardened-lab](https://github.com/AlegreGonza/ad-hardened-lab)** · lab
 
Windows Server 2022 domain in VirtualBox, built as a real administration environment.
 
- OUs by administration tier (0, 1, 2) and AGDLP group model
- Protected Users, LAPS, and Domain Admin accounts kept out of daily use
- GPOs that disable LLMNR and enforce SMB and LDAP signing
- Idempotent scripts with `-WhatIf`, deployed with Ansible; PSScriptAnalyzer in GitHub Actions
- Snapshot before each phase and a decision log
**[ctf-writeups](https://github.com/AlegreGonza/ctf-writeups)** · write-ups
 
Blue Team and DFIR CTF write-ups focused on the reasoning behind each finding, including a full forensic investigation of a Windows endpoint (Registry, SRUM, ShimCache, UserAssist, search index) and the "Paper Ghost" challenge from Holmes CTF 2026.
 
## Open source
 
**Wazuh:** reported a sshd decoder bug that failed to extract source IP and user from failed OpenSSH logins, which blocked event correlation and brute-force alerts. Reproduced on Wazuh 4.8.0 and 4.14.7 ([wazuh/wazuh#39954](https://github.com/wazuh/wazuh/issues/39954)).
 
## Speaking
 
- **NicaHackFest 2026** (NicaBuilds / NicaSecurity): talk on uptime-sentinel's design decisions, with a live alert-flow demo.
## Core skills
 
- **Detection and correlation:** custom rules, Suricata network events, Wazuh host events, false-positive reduction
- **Incident response:** triage, investigation, containment and documentation per PICERL and NIST SP 800-61
- **Digital forensics:** timeline reconstruction from Windows artifacts, time-zone normalization, cross-source correlation
- **Help desk and operations:** impact-based triage, escalation, root cause analysis, process documentation
- **Systems:** Windows Server and Active Directory, Linux, virtualization, backup and restore
- **Cloud and IaC:** serverless design, Terraform state, least-privilege IAM, free-tier cost control
- **CI/CD security:** secret scanning and static analysis of infrastructure as code
## Experience
 
**Application Support L2 / Help Desk · Pampa Net (ISP)** · Jan 2024 – Mar 2026
 
- Handled 8–10 tickets per day (billing, account access, equipment faults) in Zoho Desk, with impact-based triage and N2 escalation including root cause diagnosis
- Monitored servers and links with Zabbix and Grafana; built alerts and dashboards for failures and degradations
- Investigated incidents with Kibana/Elastic: outages, intermittent service, authentication errors, link saturation, ERP sync failures
- Built a local AI tool that adds similar-case context to ticket triage; first response time on low-impact incidents dropped from 10 to 7 minutes
- Took part in the legacy ERP → ISPCube migration: functional testing, documentation and user training
- Automated pre-registration flow (WhatsApp bot and web form) connected to the ISPCube API
- Produced monthly and quarterly reports in SQL Server
- Removed plaintext credentials and excess privileges; enforced password policy and least privilege
**Level 1 Technical Support (part-time) · NeaComputación** · Dec 2021 – Oct 2023
 
- Hardware and electronics diagnosis and repair
- Installation, configuration, backup and migration of Windows and Linux
- Small office networks: routers, switches, Wi-Fi, TCP/IP
<details>
<summary><b>Full tech stack</b></summary>
- **Security and SOC:** Suricata · Wazuh · TheHive · Cortex · Sigma · MITRE ATT&CK · Sysmon · Gitleaks · Checkov
- **Forensics:** RegRipper · SIDR · libesedb · Registry, SRUM, ShimCache, UserAssist
- **Networking and firewalls:** FortiGate · TCP/IP · DNS · DHCP · SSH · VPN · routers, switches, Wi-Fi
- **Active Directory and systems:** Windows Server · AD (GPO, OUs, LAPS, Protected Users) · Ubuntu Server · Proxmox · VMware · VirtualBox
- **Cloud and IaC:** AWS (Lambda, API Gateway, DynamoDB, CloudWatch, SNS, EventBridge) · Terraform · Ansible · Docker
- **Monitoring and logs:** Zabbix · Grafana · Kibana / Elastic · CloudWatch
- **Help desk and ITSM:** Zoho Desk · Jira · ISPCube · Odoo · Google Workspace
- **Databases:** SQL Server · MySQL · PostgreSQL · MongoDB
- **Languages and automation:** Python · PowerShell · Bash · Java · REST APIs · n8n · Git/GitHub · React · Next.js
</details>
## Education and certifications
 
- B.Sc. in Information Systems, UNNE (in progress)
- Fortinet Network Security Expert (NSE) 1, 2 and 3 (Fortinet, 2026)
- SIEM and Threat Hunting (Cisco + Splunk)
- Networking Basics (Cisco Networking Academy)
- Full Stack Web Development Bootcamp (React and Next.js), ITBA
- Data and Cloud Bootcamp, DEVLIGHTS
## Frameworks
 
PICERL (SANS) · NIST SP 800-61 · MITRE ATT&CK
 
## Languages
 
Spanish (native) · English (B1, technical reading and writing) · Portuguese (B1)
 
---
 
<p align="center">
  <a href="https://www.linkedin.com/in/alegregonzalos/"><img src="https://img.shields.io/badge/Let's_connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn"></a>
  <a href="https://github.com/AlegreGonza?tab=repositories"><img src="https://img.shields.io/badge/See_all_repos-111827?style=for-the-badge&logo=github&logoColor=white" alt="See all repositories"></a>
</p>
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:22d3ee,100:0b1020&height=120&section=footer" alt="" width="100%">
</p>
 
 
 
