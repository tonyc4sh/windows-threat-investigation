 Attack Timeline

This timeline summarizes the observed attacker activity reconstructed from the Procmon capture.

| Time | Activity | Description | ATT&CK (optional) |
|------|----------|-------------|-------------------|
| 07:18:50 | Initial Remote Execution | `wmiprvse.exe` spawned `cmd.exe` under the `MSEDGEWIN10\helpdesk` account. Output redirected to the ADMIN$ share, indicating possible remote WMI execution. | T1047 - WMI |
| 07:19 | Host Reconnaissance | Execution of `whoami`, `ipconfig`, `net user`, `net localgroup`, `net share`, and `wmic` to enumerate the environment. | T1082 / T1033 / T1016 |
| 07:20 | Microsoft Defender Tampering | PowerShell executed `Set-MpPreference -DisableRealtimeMonitoring`, disabling real-time protection. | T1562.001 |
| 07:21 | Credential Dumping Preparation | Registry hives `SAM` and `SYSTEM` exported using `reg save`. | T1003.002 |
| 07:22 | Suspicious Payload Execution | `SJi8hednh12.exe` executed and spawned multiple child processes including PowerShell and Certutil. | T1204 |
| 07:23 | PowerShell Execution Policy Bypass | PowerShell launched with `-ep bypass`, bypassing execution policy restrictions. | T1059.001 |
| 07:24 | Payload Download | `certutil.exe` downloaded `down.ps1` from `54.237.236.103`. | T1105 |
| 07:26 | Additional Payload Execution | Execution of `passed.exe` and `br0298.exe`, indicating further post-exploitation activity. | T1204 |
| 07:28 | Connectivity Verification | `ping 1.1.1.1` executed to verify outbound network connectivity. | T1016 |
| 07:29 | Archive Creation | `tar.exe` created `de.zip`, possibly preparing collected data for exfiltration or staging. | T1560 |

---

## High-Level Attack Flow

```text
Remote WMI Execution
        │
        ▼
Host Reconnaissance
        │
        ▼
Defender Disabled
        │
        ▼
Credential Dumping
        │
        ▼
Payload Execution
        │
        ▼
Payload Download (certutil)
        │
        ▼
Additional Malware Execution
        │
        ▼
Archive Creation
```

## Assessment

The observed activity is consistent with a hands-on-keyboard intrusion involving:

- Remote administration through WMI
- Host reconnaissance
- Defense evasion
- Credential access
- Living-off-the-Land techniques
- Payload staging
- Possible preparation for lateral movement or data exfiltration
