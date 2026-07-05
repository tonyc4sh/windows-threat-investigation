# Windows Threat Investigation using Procmon

> **Blue Team • Threat Hunting • Digital Forensics • Incident Response**

---

## Overview

This repository contains an independent forensic investigation of a Windows security incident based on a Microsoft Process Monitor (Procmon) capture provided as part of a cybersecurity technical assessment.

The objective was to reconstruct the attack timeline, identify Indicators of Compromise (IOCs), analyze attacker behaviour and produce an executive-level incident report suitable for a Security Manager or CISO.

---

## Skills Demonstrated

- Incident Investigation
- Threat Hunting
- Process Tree Analysis
- Timeline Reconstruction
- IOC Extraction
- Windows Internals
- Living-off-the-Land (LOLBIN) Detection
- Executive Reporting

---

## Investigation Workflow

```text
Procmon Capture
      │
      ▼
Process Tree Analysis
      │
      ▼
Timeline Reconstruction
      │
      ▼
IOC Extraction
      │
      ▼
Behaviour Analysis
      │
      ▼
Executive Report
```

---

## Repository Contents

| Folder | Description |
|---------|-------------|
| **docs/** | Investigation report, attack timeline, IOCs and lessons learned |
| **screenshots/** | Screenshots supporting the investigation findings |

---

## Documentation

- 📄 Incident Investigation Report
- 📅 Attack Timeline
- 🎯 Indicators of Compromise (IOCs)
- 📚 Lessons Learned

---

## Tools Used

- Microsoft Process Monitor (Procmon)
- Microsoft Sysinternals Suite

---

## Key Findings

The investigation identified several post-compromise activities including:

- Remote WMI-based execution
- Host reconnaissance
- Microsoft Defender tampering
- Credential dumping
- PowerShell execution policy bypass
- Living-off-the-Land (LOLBIN) abuse
- Remote payload retrieval
- Additional post-exploitation activity

---

## Future Improvements

- Correlate findings with Sysmon telemetry
- Create Sigma detection rules
- Develop Wazuh detection rules
- Map techniques using MITRE ATT&CK Navigator
- Extend the investigation using Windows Event Logs

---

## Dataset Notice

The dataset analysed in this repository originated from a publicly distributed technical assessment.

This repository demonstrates my investigation methodology, documentation quality and incident analysis process. It does **not** claim ownership of the original dataset.

---

## Author

This project is part of my personal cybersecurity portfolio and documents my practical learning journey in Blue Team operations, Incident Response and Digital Forensics.
