# Splunk Detection Content

## Purpose
To detect and analyse suspicious activity generated within the lab environment.

## Scope
Covers host-based and network-based log sources ingested into Splunk.

## Environment
- Splunk Free
- Linux log sources
- Windows event logs

## Implementation
Custom searches were created to identify authentication failures, suspicious command execution, and anomalous network behaviour.

## Validation
Alerts were triggered successfully during simulated attack activity.

## Security Considerations
Log sources contain no sensitive personal data and are limited to lab hosts.

## Notes / Lessons Learned
Search tuning reduced false positives during baseline activity.
