# Lessons Learned

## What I learned

- Investigating Procmon telemetry at scale
- Reconstructing attacker timelines
- Identifying LOLBIN abuse
- Correlating parent-child process relationships
- Extracting Indicators of Compromise
- Writing executive-level incident reports

## Challenges

- Procmon does not provide complete visibility into the initial access vector.
- Some conclusions required behavioural analysis rather than direct evidence.
- Certain attacker actions could only be inferred from surrounding telemetry.

## Future Improvements

- Correlate Procmon with Sysmon events.
- Import IOCs into Sigma or Wazuh detection rules.
- Map all findings to MITRE ATT&CK Navigator.
