### Gonzalo Alegre
POCTF:INC3AURY
**Cybersecurity Analyst · Blue Team · Detection & Incident Response**

[LinkedIn](https://www.linkedin.com/in/alegregonzalos/) · [SOC Home Lab](https://github.com/AlegreGonza/soc-home-lab)

---

### About

Cybersecurity analyst and Information Systems student, focused on defensive security.

This profile is where I document that process: a self-built SOC environment that I design, operate, and attack myself, with every incident investigated and written up the way a real SOC case would be.

My focus is detection, event correlation, and incident response as part of a SOC team.

### Current focus

- Building a self-hosted SOC stack (Suricata + Wazuh + TheHive + Cortex), running controlled attacks against it, and documenting each incident end to end.
- Deepening detection engineering with Sigma rules, SOAR automation, and MITRE ATT&CK mapping.
- Applying standard incident response methodologies: SANS PICERL and NIST SP 800-61.

### Featured projects

| Project | Description |
|---|---|
| **[soc-home-lab](https://github.com/AlegreGonza/soc-home-lab)** | Detection and incident-response lab built from scratch. Real attacks executed against real machines, detected in real time, investigated, and documented as complete incident reports mapped to MITRE ATT&CK — including the blind spots the stack doesn't catch. |
| **[ctf-writeups](https://github.com/AlegreGonza/ctf-writeups)** | Blue Team / DFIR challenge write-ups, focused on the analytical reasoning behind each finding. Includes a full Windows endpoint forensics investigation (Registry, SRUM, ShimCache, UserAssist, Windows Search index). |

### How the lab works

```
Controlled attack  →  Detection (Suricata / Wazuh)  →  Correlation & alerting
        →  Case management (TheHive)  →  Enrichment (Cortex)
        →  Incident report (PICERL + MITRE ATT&CK)  →  Rule improvement
```

### Technical stack

- **SIEM / IDS:** Wazuh, Suricata, Sigma
- **SOAR / Case management:** TheHive, Cortex
- **Frameworks & methodologies:** MITRE ATT&CK, SANS PICERL, NIST SP 800-61
- **Digital forensics (Windows):** Registry hives, SRUM, ShimCache, UserAssist, Windows Search index (RegRipper, SIDR, libesedb)
- **Systems & infrastructure:** Linux, Windows, Docker
- **Networking:** TCP/IP, DNS
- **Programming & data:** Python, Java, SQL (university coursework and personal projects)

### Core competencies

- **Detection & correlation:** custom detection rules, correlation between network events (Suricata) and host events (Wazuh), false-positive reduction.
- **Incident response:** alert triage, investigation, containment, and documentation following SANS PICERL and NIST SP 800-61.
- **Digital forensics:** timeline reconstruction from Windows artifacts, time-zone normalization, correlation across independent sources by shared identifiers.
- **Threat mapping:** classifying adversary activity by MITRE ATT&CK tactics and techniques.
- **Infrastructure troubleshooting:** Docker networking, Linux permissions, SOAR integration diagnostics.

### Certifications

- Cybersecurity Defense Analyst Career Path — Cisco + Splunk
- Networking Basics — Cisco Networking Academy

---
