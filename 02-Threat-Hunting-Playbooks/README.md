
#  Threat Hunting, KQL & Active Defence Playbooks

<p align="left">
  <img src="https://img.shields.io/badge/Microsoft%20Sentinel-0078D4?style=flat-square&logo=microsoft&logoColor=white">
  <img src="https://img.shields.io/badge/KQL-8A2BE2?style=flat-square&logo=microsoft&logoColor=white">
  <img src="https://img.shields.io/badge/Microsoft%20Defender-0047AB?style=flat-square&logo=microsoft&logoColor=white">
   <img src="https://img.shields.io/badge/Sysmon-FF69B4?style=flat-square&logo=windows&logoColor=white" alt="Sysmon" />
  <img src="https://img.shields.io/badge/MITRE_ATT%26CK-4B0082?style=flat-square">
  <img src="https://img.shields.io/badge/MITRE_D3FEND-00008B?style=flat-square">
</p>
This directory contains a collection of professional threat-hunting playbooks and cyber deception (honeytoken) strategies, designed to demonstrate practical SOC Analyst (Blue Team) skills using Microsoft Defender, Microsoft Sentinel, Sysmon telemetry, and MITRE frameworks (ATT&CK / D3FEND).

Rather than following a rigid template, these documents adapt to the specific nature of the threat—whether proactively hunting for compromised cloud identities or deploying active defence decoys on an endpoint. 

Across this directory, you will find a combination of:

* ➡️ **Hunt Hypotheses & Clear Objectives:** Defining what we are looking for or trapping.
* ➡️ **Attack Vectors & Impact:** Understanding how the adversary operates.
* ➡️ **Detection Logic & Decoy Setup:** Using KQL to surface anomalies or configuring high-fidelity SIEM alerts.
* ➡️ **Investigation Workflows:** Step-by-step event triage, proof of concepts, and log correlation.
* ➡️ **Red Flags & IoCs:** Key indicators of malicious behaviour or active compromise.
* ➡️ **Containment Procedures:** Recommended SOC response actions to isolate the threat.

---

## ➡️ Contents

### 1. [PowerShell Encoded Command Hunting](/02-Threat-Hunting-Playbooks/powershell-encoded/hunting.md)
- **MITRE ATT&CK:** `T1059.001 — Command and Scripting Interpreter: PowerShell`
- **Overview:** Detects the use of Base64-encoded PowerShell commands, a common technique for hiding malicious payloads, downloading remote scripts, executing C2 stagers, and evading basic logging.

### 2. [OS Credential Dumping & LSASS Access Hunting](/02-Threat-Hunting-Playbooks/lsass-access/hunting.md)
- **MITRE ATT&CK:** `T1003 — OS Credential Dumping`
- **Overview:** Identifies attempts to access LSASS or explorer.exe memory using tools such as ProcDump and Mimikatz. Includes KQL correlation with outbound network exfiltration and automated SOAR response.

### 3. [Authentication Anomalies & Entra ID Hunting](/02-Threat-Hunting-Playbooks/authentication-anomalies/README.md)
- **MITRE ATT&CK:** `T1078 — Valid Accounts`
- **Overview:** Detects suspicious authentication patterns in the cloud, focusing on impossible travel, MFA fatigue, and brute-force spikes using custom Kusto Query Language (KQL) bins.

### 4. [Active Defence: Honeytokens & Cyber Deception](/02-Threat-Hunting-Playbooks/active-defence-honeytokens/active-defence-honeytokens.md)
- **MITRE D3FEND:** `D3-DO Decoy Object`
- **Overview:** Demonstrates the deployment of file-based honeytokens (decoy files) to generate high-fidelity, zero-false-positive alerts in Microsoft Sentinel when adversaries attempt to access sensitive directories.

---

## ➡️ Purpose of This Directory ⬅️

This directory bridges my professional background in high-volume logistics with Blue Team operations. 

In my daily work as a Perpetual Inventory and Systems Specialist within a fast-paced distribution centre, my core responsibility is investigating complex discrepancies. This involves correlating events across multiple enterprise systems (such as WMS and ERPs), validating multi-source data, and reconstructing operational timelines to identify the root cause of an anomaly.

I have directly translated this analytical methodology into my SOC workflow. The same methodical approach I use to triage system anomalies and resolve critical discrepancies is what I apply here to:

* Conduct proactive threat-hunting investigations.
* Correlate identity, process, network, and file telemetry to uncover hidden adversary behaviours.
* Implement active defence mechanisms (honeytokens) to generate high-fidelity alerts.
* Document findings with the clarity, precision, and operational focus required in a real-world environment.

---
 ## ➡️ Connect with me

[![Magda Dominguez LinkedIn](https://img.shields.io/badge/LinkedIn-Magda_Dominguez-9370DB?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/magda-d-infosec)
