# SSH Brute Force Detection

## Objective
Detect repeated SSH authentication failures from a single source IP witrhin a short time window.

## Data Source
- Host: ubuntusplunk (Ubuntu 24.04)
- Log: `/var/log/auth.log`
- Index: `lab_auth`
- Sourcetype: `linux_secure`

## Notes on Ubuntu Log Format
Ubuntu may not log `Failed password` for every SSH failure. Common patterns include:
- `pam_unix(sshd:auth): authentication failure`
- `PAM X more authentication failures`
This can create multiple events per login attempt, so counts may be inflated if not tuned.

## SPL – Authentication Failures (by source IP)
```spl
index=lab_auth sourcetype=linux_secure ssh "authentication failure"
| rex "rhost=(?<src_ip>\d+\.\d+\.\d+\.\d+)"
| stats count as events by src_ip, user
| sort - events
```

## SPL – Brute Force Detection (Thresholded, 5-Minute Window)

```spl
index=lab_auth sourcetype=linux_secure ssh
| rex "rhost=(?<src_ip>\d+\.\d+\.\d+\.\d+)"
| bin _time span=5m
| stats count as events by _time src_ip
| where events >= 3
| sort - _time
```

## Tuning & Noise Reduction

- Increase threshold in larger environments (e.g. 5–10 failures per 5 minutes)
- Adjust time window based on environment sensitivity
- Exclude local or known management IPs to reduce noise:

```spl
| where src_ip!="127.0.0.1" AND src_ip!="10.10.10.50"
```

## MITRE ATT&CK Mapping

- **T1110 – Brute Force**
  - Tactic: Credential Access
  - Technique: SSH authentication attempts

This detection aligns with early-stage credential access and can be used as a precursor signal for lateral movement.



