<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=24&pause=1000&color=3B82F6&center=true&vCenter=true&width=700&lines=Cybersecurity+Analyst;Blue+Team+%7C+SOC+Detection;Cloud+%26+Infrastructure+on+AWS" alt="Typing animation" />

### Gonzalo Alegre

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alegregonzalos/)
[![SOC Lab](https://img.shields.io/badge/SOC_Lab-111827?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AlegreGonza/soc-home-lab)
[![uptime-sentinel](https://img.shields.io/badge/uptime--sentinel-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)](https://github.com/AlegreGonza/uptime-sentinel)

</div>

---

### About

Cybersecurity analyst and Information Systems student, focused on defensive security and the infrastructure it depends on. More than two years of help desk and application support at an ISP, handling incidents on Windows Server, Linux, and internal management systems, with root-cause diagnosis and documentation for each case.

I document my work as complete projects: a self-built SOC lab where I design, operate, and attack my own setup, and a serverless cloud project deployed on AWS with Terraform. Each incident in the SOC lab is documented as a case, the way a real SOC would record it.

### Current focus

- Building a self-hosted SOC lab (Suricata + Wazuh + TheHive), running controlled attacks, and documenting each case end to end.
- Deepening detection engineering with Sigma rules, SOAR automation, and MITRE ATT&CK mapping.
- Deepening firewall skills with FortiGate, building on Fortinet NSE 1–3 certifications.
- Applying incident response methodologies: SANS PICERL and NIST SP 800-61.

### Tech stack

<div align="center">

**Security & SOC**

![Wazuh](https://img.shields.io/badge/Wazuh-0E7C86?style=flat-square)
![Suricata](https://img.shields.io/badge/Suricata-EF3B24?style=flat-square)
![TheHive](https://img.shields.io/badge/TheHive-FFCC00?style=flat-square&logoColor=black)
![Sigma](https://img.shields.io/badge/Sigma-3B82F6?style=flat-square)
![MITRE ATT&CK](https://img.shields.io/badge/MITRE_ATT%26CK-E60000?style=flat-square)
![FortiGate](https://img.shields.io/badge/FortiGate-EE3124?style=flat-square)

**Cloud, IaC & DevSecOps**

[![AWS](https://skillicons.dev/icons?i=aws)](https://aws.amazon.com/)
[![Terraform](https://skillicons.dev/icons?i=terraform)](https://www.terraform.io/)
[![Ansible](https://skillicons.dev/icons?i=ansible)](https://www.ansible.com/)
[![Docker](https://skillicons.dev/icons?i=docker)](https://www.docker.com/)
[![GitHub](https://skillicons.dev/icons?i=github)](https://github.com/AlegreGonza)

**Systems & Languages**

[![Linux](https://skillicons.dev/icons?i=linux)](https://ubuntu.com/)
[![Windows](https://skillicons.dev/icons?i=windows)](https://www.microsoft.com/windows-server)
[![PowerShell](https://skillicons.dev/icons?i=powershell)](https://learn.microsoft.com/powershell/)
[![Bash](https://skillicons.dev/icons?i=bash)](https://www.gnu.org/software/bash/)
[![Python](https://skillicons.dev/icons?i=python)](https://www.python.org/)
[![Java](https://skillicons.dev/icons?i=java)](https://www.java.com/)

**Databases**

[![MySQL](https://skillicons.dev/icons?i=mysql)](https://www.mysql.com/)
[![PostgreSQL](https://skillicons.dev/icons?i=postgres)](https://www.postgresql.org/)
[![MongoDB](https://skillicons.dev/icons?i=mongodb)](https://www.mongodb.com/)

</div>

**Networking:** TCP/IP, DNS, DHCP, SSH, VPN, router/switch/Wi-Fi configuration, FortiGate firewalls (Fortinet NSE 1–3 certified).
**Systems:** Windows Server, Active Directory (GPOs, OUs, LAPS, Protected Users), Proxmox, VMware, VirtualBox.
**IT support & ITSM:** Zoho Desk, Jira, ISPCube, Odoo, Google Workspace. Impact-based triage, N1/N2 escalation, SLAs.
**Forensics:** Registry hives, SRUM, ShimCache, UserAssist, Windows Search index (RegRipper, SIDR, libesedb).
**Applied AI:** local AI model that enriches help desk triage with context from past cases.

### Experience

**Application Support, Level 2 (help desk) — Pampa Net (ISP)** · Jan 2024 – Mar 2026
- Handled 8 to 10 tickets per day (billing, account access, equipment failures), with root-cause diagnosis and escalation to N2.
- Built a local AI tool that enriches each ticket with context from similar cases, cutting first-response time on low-impact incidents from 10 to 7 minutes.
- Took part in migrating clients and processes from a legacy ERP to ISPCube, with functional testing and user training.
- Built an automated pre-registration flow (WhatsApp bot and web form) connected to the ISPCube API.
- Produced monthly SQL reports (SELECT, JOIN, aggregations, subqueries) on SQL Server.
- Removed plain-text credentials and excess privileges, and applied password and least-privilege policies.

**Technical Support (part-time) — NeaComputación** · Dec 2021 – Oct 2023
- Hardware and electronics repair, plus Windows and Linux installation, configuration, backup, and migration.
- Set up small office networks (routers, switches, Wi-Fi, TCP/IP).

### Featured projects

<table>
<tr>
<td width="50%" valign="top">

#### [uptime-sentinel](https://github.com/AlegreGonza/uptime-sentinel)
Serverless uptime monitor on AWS with a risk index, deployed with Terraform. Checks sites every 5 minutes, stores history in DynamoDB, and sends email alerts (pre-alert, down, recovery, risk index). A CloudWatch alarm detects if the monitor stops running.

The checker includes SSRF protections (HTTPS only, DNS validation, rejection of non-public addresses, IP pinning). CI runs Gitleaks and Checkov. MIT licensed.

![AWS](https://img.shields.io/badge/AWS_Lambda-FF9900?style=flat-square&logo=awslambda&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)

</td>
<td width="50%" valign="top">

#### [soc-home-lab](https://github.com/AlegreGonza/soc-home-lab)
Work-in-progress SOC detection and incident-response lab. Attacks launched from Kali against an Ubuntu server, monitored by Suricata (NIDS) and Wazuh (HIDS and file integrity monitoring). Wazuh alerts are promoted to TheHive cases automatically.

Documented case: SSH brute force and data exfiltration, mapped to MITRE ATT&CK and organized by PICERL. Includes documented blind spots (commands without sudo leave no trace; encrypted SSH/SCP hides content from NIDS).

![Wazuh](https://img.shields.io/badge/Wazuh-0E7C86?style=flat-square)
![Suricata](https://img.shields.io/badge/Suricata-EF3B24?style=flat-square)
![TheHive](https://img.shields.io/badge/TheHive-FFCC00?style=flat-square&logoColor=black)

</td>
</tr>
<tr>
<td width="50%" valign="top">

#### [ctf-writeups](https://github.com/AlegreGonza/ctf-writeups)
Blue Team and DFIR challenge write-ups, focused on the analytical reasoning behind each finding. Includes a full Windows endpoint forensics investigation (Registry, SRUM, ShimCache, UserAssist, Windows Search index).

![DFIR](https://img.shields.io/badge/DFIR-111827?style=flat-square)
![Forensics](https://img.shields.io/badge/Forensics-111827?style=flat-square)

</td>
<td width="50%" valign="top">

#### Open source contribution
**Wazuh:** reported a decoder issue in the sshd decoder ([wazuh/wazuh#39954](https://github.com/wazuh/wazuh/issues/39954)). It did not extract source IP or user from failed OpenSSH authentication events, which blocked correlation and brute-force alerts. Reproduced on Wazuh 4.8.0 and 4.14.7, mapped to MITRE ATT&CK T1110.001.

</td>
</tr>
</table>

### How the labs work

**SOC lab**
```
Controlled attack  →  Detection (Suricata / Wazuh)  →  Case management (TheHive)
        →  Incident report (PICERL + MITRE ATT&CK)  →  Rule improvement
```

**uptime-sentinel**
```
EventBridge (every 5 min)  →  Monitor Lambda  →  Checker Lambda
        →  DynamoDB (history)  →  SNS (email alerts)
```

### Core competencies

- **Detection & correlation:** custom rules, correlation of network (Suricata) and host (Wazuh) events, false-positive reduction.
- **Incident response:** triage, investigation, containment, and documentation following PICERL and NIST SP 800-61.
- **Help desk & operations:** impact-based triage, escalation, root-cause analysis, process documentation.
- **Systems administration:** Windows Server and Active Directory, Linux, virtualization, backup and restore.
- **Digital forensics:** timeline reconstruction from Windows artifacts, time-zone normalization, cross-source correlation.
- **Cloud & IaC:** serverless architecture, Terraform state management, least-privilege IAM, free-tier cost control.
- **Security in CI/CD:** secret scanning and infrastructure-as-code static analysis.

<div align="center">

[![View all repositories](https://img.shields.io/badge/View_all_repositories-111827?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AlegreGonza?tab=repositories)

</div>

### Education & certifications

- Bachelor's degree in Information Systems (in progress)
- DEVLIGHTS Bootcamp: Data and Cloud
- Fortinet Network Security Expert (NSE) 1, 2 and 3 (Fortinet, 2026)
- SIEM and Threat Hunting — Cisco + Splunk
- Networking Basics — Cisco Networking Academy

### Languages

Spanish (native) · English (B1)

<div align="center">

[![LinkedIn](https://img.shields.io/badge/Let's_connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/alegregonzalos/)

</div>
