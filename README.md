# Snort IDS Deployment & Custom Detection Rules

Installation, configuration and testing of the **Snort** network intrusion detection system, with custom rules to detect common reconnaissance and attack traffic generated from a Kali Linux attacker.

**Full write-up:** [writeup.md](writeup.md)

## What's Covered

- Current challenges in IDS deployment (false positives/negatives, encrypted traffic, evasion, zero-days)
- How attackers exploit IDS weaknesses, with a case study of the **Colonial Pipeline** ransomware attack (2021)
- Best practices for effective IDS deployment
- Why Snort compared with other IDS tools
- **Hands-on:** installing Snort 2.9 on a Linux VM, configuring `snort.conf`, and writing custom rules in `local.rules`
- Running Snort in console alert mode and validating detections with traffic from Kali

## Example Custom Rules

```
alert icmp any any -> $HOME_NET any (msg:"ICMP Ping Detected"; sid:100001; rev:1;)
alert tcp $EXTERNAL_NET any -> $HOME_NET any (msg:"TCP SYN Scan Detected"; flags:S; sid:100002; rev:1;)
```

The rule set covers ICMP ping sweeps, TCP SYN scans, FTP login attempts and other unauthorised access attempts.

## Tools

Snort 2.9 · Linux · Kali Linux · Nmap / ping · VirtualBox
