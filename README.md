### Gonzalo Alegre
**Cybersecurity Analyst · Blue Team · Systems Administration & Cloud Infrastructure**

[LinkedIn](https://www.linkedin.com/in/alegregonzalos/) · [SOC Home Lab](https://github.com/AlegreGonza/soc-home-lab) · [uptime-sentinel](https://github.com/AlegreGonza/uptime-sentinel)

---

### About

Cybersecurity analyst and Information Systems student, focused on defensive security and the infrastructure it depends on. More than two years of help desk and application support experience at an ISP, handling incidents on Windows Server, Linux, and internal management systems, with root-cause diagnosis and documentation for each case.

I document my work as complete projects: a self-built SOC lab where I design, operate, and attack my own setup, and a serverless cloud project deployed on AWS with Terraform. Each incident in the SOC lab is documented as a case, the way a real SOC would record it.

My focus is detection, event correlation, and incident response as part of a SOC team, with solid foundations in networking, Linux, Windows Server, and cloud infrastructure.

### Current focus

- Building a self-hosted SOC lab (Suricata + Wazuh + TheHive), running controlled attacks against it, and documenting each case end to end.
- Deepening detection engineering with Sigma rules, SOAR automation, and MITRE ATT&CK mapping.
- Deepening firewall skills with FortiGate, building on Fortinet NSE 1–3 certifications.
- Applying standard incident response methodologies: SANS PICERL and NIST SP 800-61.

### Experience

**Application Support, Level 2 (help desk) — Pampa Net (ISP)** · Jan 2024 – Mar 2026
- Handled 8 to 10 help desk tickets per day (billing, account access, and equipment failures), with root-cause diagnosis and escalation to N2 when needed.
- Built a local AI tool that enriches each ticket with context from similar past cases, reducing first-response time on low-impact incidents from 10 to 7 minutes.
- Took part in migrating clients and processes from a legacy ERP to ISPCube, with functional testing and user training.
- Built an automated pre-registration flow (WhatsApp bot and web form) connected to the ISPCube API.
- Produced monthly reports with SQL (SELECT, JOIN, aggregations, subqueries) on SQL Server.
- Improved access security by removing plain-text credentials and excess privileges, and applying password and least-privilege policies.

**Technical Support (part-time) — NeaComputación** · Dec 2021 – Oct 2023
- Hardware and electronics diagnosis and repair, along with Windows and Linux installation, configuration, backup, and migration.
- Set up small office networks (routers, switches, Wi-Fi, TCP/IP) and Windows/Linux systems.

### Featured projects

| Project | Description |
|---|---|
| **[uptime-sentinel](https://github.com/AlegreGonza/uptime-sentinel)** | Serverless uptime monitor on AWS with a risk index, deployed with Terraform. Checks sites every 5 minutes, stores history in DynamoDB, and sends email alerts (pre-alert, down, recovery, and risk index). A CloudWatch alarm detects if the monitor itself stops running. Exposes a protected API (API Gateway) and a CLI. The checker includes SSRF protections (HTTPS only, DNS validation, rejection of non-public addresses, and IP pinning). CI pipeline with Gitleaks (secret scanning) and Checkov (Terraform misconfiguration scanning). MIT licensed. |
| **[soc-home-lab](https://github.com/AlegreGonza/soc-home-lab)** | Work-in-progress SOC detection and incident-response lab. Attacks launched from Kali against an Ubuntu server monitored by Suricata (NIDS) and Wazuh (HIDS and file integrity monitoring). Wazuh alerts are promoted to TheHive cases automatically, and detection rules are written in Sigma and converted to Wazuh format. Documented case: SSH brute force and data exfiltration, mapped to MITRE ATT&CK and organized by PICERL. Includes documented blind spots, such as commands run without sudo leaving no trace in the audit pipeline and encrypted SSH/SCP hiding content from NIDS and logs. |
| **[ctf-writeups](https://github.com/AlegreGonza/ctf-writeups)** | Blue Team / DFIR challenge write-ups, focused on the analytical reasoning behind each finding. Includes a full Windows endpoint forensics investigation (Registry, SRUM, ShimCache, UserAssist, Windows Search index). |

### Open source contributions

- **Wazuh:** reported a decoder issue in the sshd decoder ([wazuh/wazuh#39954](https://github.com/wazuh/wazuh/issues/39954)). It did not extract source IP or user from failed OpenSSH authentication events, which prevented correlating them and generating brute-force alerts. Reproduced with wazuh-logtest on Wazuh 4.8.0 and 4.14.7, with OpenSSH 8.9p1 and 10.2p1, and mapped to MITRE ATT&CK (T1110.001).

### How the labs work

**SOC lab:**
```
Controlled attack  →  Detection (Suricata / Wazuh)  →  Case management (TheHive)
        →  Incident report (PICERL + MITRE ATT&CK)  →  Rule improvement
```

**uptime-sentinel:**
```
EventBridge (every 5 min)  →  Monitor Lambda  →  Checker Lambda
        →  DynamoDB (history)  →  SNS (email alerts)
```

### Technical stack

- **IT support & ITSM:** Zoho Desk, Jira, ISPCube, Odoo, Google Workspace. Impact-based triage, N1/N2 escalation, root-cause diagnosis, case documentation, SLAs
- **SIEM / IDS:** Wazuh, Suricata, Sigma
- **Case management:** TheHive (Cortex planned)
- **Systems & servers:** Windows Server, Windows 10/11, Linux (Ubuntu Server), Proxmox, VMware, VirtualBox
- **Active Directory & access security:** users, groups, and OUs, GPOs, Protected Users, LAPS, least privilege
- **Networking:** TCP/IP, DNS, DHCP, SSH, VPN, router/switch/Wi-Fi configuration, connectivity troubleshooting. Firewalls: FortiGate (Fortinet NSE 1–3 certified)
- **Cloud & IaC:** AWS (Lambda, API Gateway, DynamoDB, SNS, EventBridge, CloudWatch, IAM), Terraform
- **DevSecOps:** GitHub Actions, Gitleaks, Checkov, PSScriptAnalyzer
- **Automation & scripting:** PowerShell, Bash, Python (boto3, pytest, Typer), Ansible, n8n, REST APIs, Git/GitHub
- **Databases:** SQL Server, MySQL, PostgreSQL, MongoDB
- **Frameworks & methodologies:** MITRE ATT&CK, SANS PICERL, NIST SP 800-61
- **Digital forensics (Windows):** Registry hives, SRUM, ShimCache, UserAssist, Windows Search index (RegRipper, SIDR, libesedb)
- **Applied AI:** local AI model to enrich help desk triage with context from past cases

### Core competencies

- **Detection & correlation:** custom detection rules, correlation between network events (Suricata) and host events (Wazuh), false-positive reduction.
- **Incident response:** alert triage, investigation, containment, and documentation following SANS PICERL and NIST SP 800-61.
- **Help desk & operations:** impact-based triage, escalation, root-cause analysis, and process documentation.
- **Systems administration:** Windows Server and Active Directory administration, Linux, virtualization, and backup and restore.
- **Digital forensics:** timeline reconstruction from Windows artifacts, time-zone normalization, correlation across independent sources by shared identifiers.
- **Cloud & infrastructure as code:** serverless architecture, Terraform state management, least-privilege IAM, cost control within free tier.
- **Security in CI/CD:** secret scanning and infrastructure-as-code static analysis.
- **Threat mapping:** classifying adversary activity by MITRE ATT&CK tactics and techniques.

### Education

- Bachelor's degree in Information Systems (in progress)
- DEVLIGHTS Bootcamp: Data and Cloud

### Certifications

- Fortinet Network Security Expert (NSE) 1, 2 and 3 (Fortinet, 2026)
- SIEM and Threat Hunting — Cisco + Splunk
- Networking Basics — Cisco Networking Academy

### Languages

- Spanish (native)
- English (B1)
