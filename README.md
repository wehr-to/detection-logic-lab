# 🧠 detection-logic-lab

This repository is dedicated to building **real-world detection engineering skills** — turning raw event data into meaningful, high-signal alerts mapped to attacker behavior. It includes Sigma-to-KQL conversions, custom rules for Wazuh, Sysmon, and Auditd, enrichment strategies, MITRE mappings, and lab simulations to stress-test your detection logic.

## 🎯 Why This Repo Exists

Anyone can collect logs. Anyone can trigger alerts.

But **real detection engineering** requires:

- Mapping behavior to telemetry
- Tuning rules to reduce false positives
- Enriching alerts with context
- Prioritizing signal over volume

This repo reflects that mindset: not just alerting — **precision signal engineering.**

## 🔍 What's Covered

| Area                    | Description |
|-------------------------|-------------|
| `sigma-to-kql/`         | Converting Sigma rules into Azure KQL queries |
| `detection-logic/`      | Custom Wazuh, Sysmon, and auditd detection rules |
| `tuning-and-enrichment/`| Frameworks for reducing false positives and adding context |
| `mitre-mapping/`        | Each detection tied to real TTPs from MITRE ATT&CK |
| `detection-labs/`       | Simulated attack scenarios to test rule effectiveness |
| `dashboards/`           | Sample Kibana, Graylog, and Grafana visualizations |

## ⚙️ Sample Sigma → KQL Conversion

```yaml
title: Credential Dumping via LSASS Access
detection:
  selection:
    EventID: 10
    TargetImage: lsass.exe
  condition: selection

# converted to: EventID == 10 and TargetImage has "lsass.exe"

## 🔧 Custom Wazuh Rule Example
<rule id="100012" level="10">
  <if_sid>18107</if_sid>
  <match>login failed for user 'sa'</match>
  <description>Potential brute-force login attempt on MSSQL</description>
</rule>

## 📘 MITRE Technique Mapping
| TTP       | Description                        |
| --------- | ---------------------------------- |
| T1003     | Credential Dumping (e.g., LSASS)   |
| T1059     | Command-Line Interface Abuse       |
| T1071.004 | Exfiltration Over DNS              |
| T1547     | Persistence via Startup Mechanisms |
| T1055     | Process Injection Techniques       |

## 🧪 Detection Labs Included

| Lab Scenario              | What You'll Learn                                     |
| ------------------------- | ----------------------------------------------------- |
| `brute-force-sim.md`      | Detecting login failures with tuning for FP reduction |
| `dns-tunneling-lab.md`    | Detecting long query exfiltration over DNS            |
| `powershell-abuse-lab.md` | Detecting encoded and obfuscated PowerShell execution |
| `sysmon-trace-lab.md`     | Mapping process trees and command-line activity       |
| `auditd-binary-exec.md`   | Linux binary abuse and detection logic using Auditd   |
| `atomic-redteam-setup.md` | Lab setup for simulating MITRE techniques             |

## 📊 Dashboards & Alert Visualizations
- Kibana alerts mapped to TTPs
- Graylog streams with tagging logic
- Grafana panels for high-volume alert tuning

## 👥 Who Should Use This
- Detection engineers tuning high-fidelity alerts
- SOC analysts learning triage and threat prioritization
- Blue teamers building MITRE-aligned detection coverage
- Students & career switchers prepping for real interviews
- Security engineers refining telemetry-to-alert pipelines
