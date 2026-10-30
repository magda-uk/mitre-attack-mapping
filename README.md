#  MITRE ATT&CK Lab Mapping

<p align="left">
  <!-- SIEM, Telemetry & Cloud -->
  <img src="https://img.shields.io/badge/Wazuh_SIEM-00aeef?style=flat-square&logo=wazuh&logoColor=white" alt="Wazuh" />
  <img src="https://img.shields.io/badge/Microsoft_Sentinel-0047AB?style=flat-square&logo=microsoft&logoColor=white" alt="Sentinel" />
  <img src="https://img.shields.io/badge/Entra_ID-4B0082?style=flat-square&logo=microsoftazure&logoColor=white" alt="Entra ID" />
  <img src="https://img.shields.io/badge/Sysmon-FF69B4?style=flat-square&logo=windows&logoColor=white" alt="Sysmon" />
  <img src="https://img.shields.io/badge/Windows_Logs-9370DB?style=flat-square&logo=windows&logoColor=white" alt="Windows Event Logs" />
  


  <!-- Querying, Scripting & Automation -->
  <img src="https://img.shields.io/badge/KQL-1E90FF?style=flat-square&logo=azuredataexplorer&logoColor=white" alt="KQL" />
  <img src="https://img.shields.io/badge/PowerShell-483D8B?style=flat-square&logo=powershell&logoColor=white" alt="PowerShell" />
  <img src="https://img.shields.io/badge/Python_Automation-00008B?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Wireshark-1E90FF?style=flat-square&logo=wireshark&logoColor=white" alt="Wireshark" />
  
  <br>

  <!-- Adversary Emulation & Recon -->
  <img src="https://img.shields.io/badge/Kali_Linux-4B0082?style=flat-square&logo=kali-linux&logoColor=white" alt="Kali Linux" />
  <img src="https://img.shields.io/badge/Nmap-FF1493?style=flat-square&logo=nmap&logoColor=white" alt="Nmap" />
  <img src="https://img.shields.io/badge/Metasploit-8A2BE2?style=flat-square&logo=metasploit&logoColor=white" alt="Metasploit" />
</p>

 
</p>
 



Welcome to my Defensive Security & SOC Analyst portfolio. This repository documents my hands-on experience, practical investigations, and incident response playbooks, mapped directly to the **MITRE ATT&CK® framework**.

Instead of relying on simulated capture-the-flag (CTF) platforms, the investigations documented in this repository are based on **100% real-world data**. I have successfully mapped the ATT&CK tactics by actively analysing live telemetry generated from my own personal workstation (utilising Sysmon, Windows Event Logs, and Wazuh) and by triaging genuine malicious phishing campaigns captured directly within my own mailbox.

> ⚠️ **Explore the Broader Ecosystem**

> This MITRE mapping repository operates as part of a wider Security Operations framework. You can explore my full methodology, detection engineering, and automation projects across my interconnected repositories:
> * ➡️ **[SOC Analyst Master Portfolio](https://github.com/magda-uk/soc-analyst-portfolio/tree/main)**: My central hub for Blue Team operations, KQL rule creation, and advanced log analysis (translating my logistics analytical mindset into SOC practices).
> * ➡️ **[Phishing Incident Response Lab](https://github.com/magda-uk/phishing-incident-response-lab/blob/main/README.md)**: My dedicated laboratory for dissecting real-world malicious emails, extracting artefacts, and deploying Python-based SOC automation.

---

## 🔻 My Triage Methodology
While the final format of each write-up varies depending on the specific threat or system analysed, my underlying investigative approach consistently follows these core analytical stages:

* **Scenario/Alert Objective:** Defining what triggered the investigation.
* **MITRE ATT&CK Mapping:** Anchoring the threat to a specific Tactic & Technique ID.
* **Telemetry & Artefacts:** Identifying the evidence sources (Sysmon, Windows Event Logs, PCAPs).
* **Investigation Steps:** Executing step-by-step triage and false-positive filtering.
* **Conclusion & Remediation:** Delivering actionable steps to mitigate the attack.
---

## 🔻 Lab Mappings by Tactic

### 🚪 Initial Access (TA0001)
* [**Incident Report: Mercadona Brand Impersonation & SEG Evasion**](./01-MITRE-ATTACK-Investigations/TA0001-Initial-Access/Phishing-Mercadona-Evasion/README.md)
  * **T1566.002: Phishing Link**/ **T1027: Obfuscated Files or Information**
  * **Focus:** Campaign Evolution, Bayesian Poisoning, Base64 HTML Evasion, and Automated EML Parsing (Python).
* [**Phishing Incident: NHS Cloud Abuse & Base64 Tracking**](./01-MITRE-ATTACK-Investigations/TA0001-Initial-Access/Phishing-NHS-Cloud-Abuse/README.md)
  * **T1566.002: Phishing Link**
  * **Focus:** Storage.googleapis.com abuse, email headers, and tracking pixels.
* [**Entra ID False Positives: Typo (50126) vs MFA Latency (50207)**](./01-MITRE-ATTACK-Investigations/TA0001-Initial-Access/False-Positive-Entra-ID/README.md)
  * **T1078.004: Valid Accounts: Cloud Accounts**
  * **Focus:** Identity and Access Management (IAM) triage, filtering login noise from real attacks.

### ⚡ Execution (TA0002)
* [**Living-off-the-Land Binary Execution (Event 1): OEM Service Control**](./01-MITRE-ATTACK-Investigations/TA0002-Execution/README.md)
  * **T1569.002: System Services: Service Execution**
  * **Focus:** Analysing LOLBin usage, process lineage, and Sysmon XML rule creation for false-positive suppression.

### 🏃 Persistence (TA0003)
* [**SOC Lab: Local Account Creation & Persistence**](./01-MITRE-ATTACK-Investigations/TA0003-Persistence/Wazuh-Local-Account-Creation/README.md)
  * **T1136.001: Create Account: Local Account**
  * **Focus:** Windows Event Logs (4720, 4732), Wazuh SIEM, and PowerShell Evasion.
* [**False Positive Tuning: Registry Event 13 Noise**](./01-MITRE-ATTACK-Investigations/TA0003-Persistence/False-Positive-Registry-Event-13/README.md)
  * **T1547.001: Boot or Logon Autostart Execution: Registry Run Keys**
  * **Focus:** Filtering benign registry modifications (Event 13) to baseline normal system persistence.

### 📈 Privilege Escalation (TA0004)
* [**Security Event Analysis: Special Privileges Assigned (Event ID 4672)**](./01-MITRE-ATTACK-Investigations/TA0004-Privilege-Escalation/README.md)
  * **T1134: Access Token Manipulation**
  * **Focus:** Windows Event ID 4672, `SeImpersonatePrivilege`, and KQL correlation with Sysmon Event ID 1.

### 🥷 Defense Evasion (TA0005)
* [**PowerShell ScriptBlock Logging & De-obfuscation (Event 4104)**](./01-MITRE-ATTACK-Investigations/TA0005-Defense-Evasion/PowerShell-Deobfuscation-4104/README.md)
  * **T1059.001: PowerShell** / **T1027: Obfuscated Files or Information**
  * **Focus:** Hunting Base64 obfuscation and decoding ScriptBlock logs in Sysmon Event 4104.
* [**VS Code Timestomping Hands-On Evidence (Event 2)**](./01-MITRE-ATTACK-Investigations/TA0005-Defense-Evasion/False-Positive-Timestomping/README.md)
  * **T1099: Timestomp**
  * **Focus:** Identifying timestamp manipulation (MACE) and baseline file creation anomalies.
* [**Sysmon Event ID 8 (CreateRemoteThread): WerFault.exe Injection**](./01-MITRE-ATTACK-Investigations/TA0005-Defense-Evasion/False-Positive-Process-Injection/README.md)
  * **T1055: Process Injection**
  * **Focus:** False positive tuning for benign remote thread creation during Windows Error Reporting debugging.
* [**False Positive Triage: Alternate Data Streams (Event 15)**](./01-MITRE-ATTACK-Investigations/TA0005-Defense-Evasion/False-Positive-Alternate-Data-Streams/README.md)
  * **T1564.004: Hide Artifacts: NTFS File Attributes**
  * **Focus:** Explaining Mark-of-the-Web (Zone.Identifier) during standard Chrome PDF downloads.

### 🔑 Credential Access (TA0006)
* [**SOC Lab: RDP Brute Force & NLA Evasion**](./01-MITRE-ATTACK-Investigations/TA0006-Credential-Access/Wazuh-RDP-Brute-Force/README.md)
  * **T1110.001: Brute Force: Password Guessing**
  * **Focus:** Nmap Reconnaissance, xfreerdp, and Event ID 4625 Triage.
* [**Forensic Analysis: Mimikatz LSASS Access (Event 10)**](./01-MITRE-ATTACK-Investigations/TA0006-Credential-Access/Mimikatz-LSASS-Access/README.md)
  * **T1003.001: OS Credential Dumping: LSASS Memory**
  * **Focus:** ProcessAccess, PROCESS_VM_READ (0x1010), and memory dumping detection.

### 🔍 Discovery (TA0007)
* [**Log Analysis: False Positive & Reconnaissance Triage**](./01-MITRE-ATTACK-Investigations/TA0007-Discovery/README.md)
  * **T1069: Permission Groups Discovery** / **T1087: Account Discovery**
  * **Focus:** False Positive Triage, Alert Tuning, and Windows Security Logs (Event ID 4798).

### 🚶🏽‍♀️ Lateral Movement (TA0008)
* [**Security Event Analysis: Endpoint Authentication & Session Telemetry**](./01-MITRE-ATTACK-Investigations/TA0008-Lateral-Movement/README.md)
  * **T1021.002: Remote Services: SMB/Windows Admin Shares**
  * **Focus:** Analysing Logon Type 3 (Network) and Logon Type 2 (Interactive) authentication failures to detect SMB probing.

### 🗂️ Collection (TA0009)
* [**Ransomware Lab (Phase 1): Data Collection & Obfuscation**](./01-MITRE-ATTACK-Investigations/TA0040-Impact/README.md)
  * **T1005: Data from Local System** / **T1022: Data Encrypted**
  * **Focus:** (Hosted within the TA0040 Impact lab). Analysing programmatic local directory collection and Base64 obfuscation prior to the destructive phase.

### 📡 Command and Control (TA0011)
* [**SOC Lab: Sysmon Activity Correlation & Telemetry Analysis**](./01-MITRE-ATTACK-Investigations/TA0011-Command-and-Control/Sysmon-Wireshark-Correlation/README.md)
  * **T1071.001: Application Layer Protocol: Web Protocols**
  * **Focus:** Cross-Event Correlation (ProcessGuid), Wireshark PCAP Analysis, and False Positive Tuning.
* [**False Positive Triage: DNS IPv6 Resolution (Event 3)**](./01-MITRE-ATTACK-Investigations/TA0011-Command-and-Control/False-Positive-DNS-IPv6/README.md)
  * **T1071.004: Application Layer Protocol: DNS**
  * **Focus:** Analysing UDP 53 traffic, discarding DNS tunneling, and validating local subnet prefixes (/64).

### 💥 Impact (TA0040)
* [**SOC Lab: Ransomware Emulation & File Integrity Monitoring (FIM)**](./01-MITRE-ATTACK-Investigations/TA0040-Impact/README.md)
  * **T1486: Data Encrypted for Impact**
  * **Focus:** Python Data Engineering (Logistics/PI datasets), Ransomware Emulation, and Wazuh `syscheck`.

### 🏗️ Resource Development (TA0042)
* [**Burner Account Infrastructure & Rotation: 419 Scam Campaign**](./01-MITRE-ATTACK-Investigations/TA0042-Resource-Development/README.md)
  * **T1586.002: Establish Accounts: Email Accounts**
  * **Focus:** Analysing threat actor infrastructure rotation, webmail abuse (Gmail), and filter evasion tactics.

### 🔭 Reconnaissance (TA0043)
* [**Active Network Reconnaissance: Nmap SYN Scan Triage**](./01-MITRE-ATTACK-Investigations/TA0043-Reconnaissance/README.md)
  * **T1595.001: Active Scanning: Scanning IP Blocks**
  * **Focus:** Analysing IDS evasion tactics (-sS, -Pn) and OS fingerprinting impact from a Blue Team perspective.

### 📤 Exfiltration (TA0104)
* [**Threat Hunting: OS Credential Dumping & Data Exfiltration (ProcDump)**](./01-MITRE-ATTACK-Investigations/TA0104-Exfiltration/README.md)
  * **T1048: Exfiltration Over Alternative Protocol**
  * **Focus:** Multi-stage correlation (Sysmon 1, 11, 3), KQL detection engineering, and Microsoft Sentinel SOAR (Logic Apps).

---


## 🔻 Threat Hunting & D3FEND Playbooks
Beyond reactive SIEM triaging, I develop proactive KQL hunting queries and active defense mechanisms (mapped to MITRE D3FEND):

* [**PowerShell Encoded Command Hunting**](/02-Threat-Hunting-Playbooks/powershell-encoded/hunting.md) - KQL playbook to hunt Base64 obfuscation.
* [**LSASS Access Hunting**](/02-Threat-Hunting-Playbooks/lsass-access/hunting.md)- KQL playbook for memory dumping and `.dmp` file creation.
* [**Auth Anomalies Hunting**](/02-Threat-Hunting-Playbooks/authentication-anomalies/README.md) - KQL playbook targeting Impossible Travel and MFA fatigue.
* [**Active Defense: Honeytokens**](/02-Threat-Hunting-Playbooks/active-defence-honeytokens/active-defence-honeytokens.md) - Deployment of Canarytokens for zero-false-positive alerting.

---
## 🔻 Application Security & Secure Code Review
While this portfolio focuses on SOC Operations and Threat Hunting, I also have a strong background in Application Security (AppSec) and technical remediation. 

You can view my secure code review, STRIDE threat modelling, and technical remediation playbooks (Python/Flask, SQL, Pydantic) in my dedicated AppSec repository:
* [**Shelfie API: Security Assessment & Remediation Playbook**](https://github.com/magda-uk/shelfie-security-audit)

---

## 🔻 Connect with me   

**Magda Dominguez**    
Blue Team operations 🔻 SOC investigations 🔻 Logistics-to-SOC analytical mindset 

[![Magda Dominguez LinkedIn](https://img.shields.io/badge/LinkedIn-Magda_Dominguez-9370DB?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/magda-d-infosec)




> I'm actively seeking a Cyber Security / SOC role where I can bring my structured troubleshooting, log analysis, and secure architecture skills to a dedicated security team.