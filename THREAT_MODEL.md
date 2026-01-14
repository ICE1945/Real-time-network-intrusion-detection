## Goal
Detect suspicious or potentially malicious network activity in real time using passive monitoring and rule-based analysis.

## Assets We Want to Protect
- Host availability and stability (prevent DoS/abuse signals going unnoticed)
- Network services (SSH/HTTP/DB ports) from brute force and scanning
- Visibility into abnormal traffic patterns for incident response

## Attacker Assumptions
- The attacker may be internal or external
- The attacker can generate high-volume traffic, scans, or repeated connection attempts
- The attacker may try to blend into normal traffic patterns to avoid detection

## In Scope (What This IDS Tries to Detect)
- **Port scanning / recon**
  - Many destination ports in a short time window
  - Many connection attempts to multiple hosts/subnets
- **Abnormal traffic rate**
  - Unusually high SYN/connection attempt rate from a single source
  - Sudden burst of packets to a service/port
- **Suspicious protocol behavior**
  - Malformed or unusual header patterns (basic sanity checks)
  - Unexpected combinations of flags (where applicable)
- **Repeated unauthorized access attempts (behavioral)**
  - Frequent repeated attempts to the same service/port

## Out of Scope (What This IDS Does NOT Claim)
- Deep payload inspection / application-layer decoding (unless explicitly implemented)
- Full signature coverage like Suricata/Snort
- Encrypted traffic decryption (TLS/SSH contents)
- Attribution (who the attacker is) — only behavior is flagged
- Guaranteed detection of low-and-slow or highly stealthy adversaries

## Typical Deployment / Safe Use
- Run on a lab machine, VM, or controlled environment
- Use passive monitoring only (no packet injection or disruption)
- Log alerts locally for later review

## Limitations (Honest)
- Rule-based logic can produce false positives/negatives
- Thresholds may require tuning per environment
- High traffic environments may need performance optimization
