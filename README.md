# :brain: detection-logic-lab

This repository is dedicated to building **real-world detection engineering skills** — turning raw event data into meaningful, high-signal alerts mapped to attacker behavior. It includes Sigma-to-KQL conversions, custom rules for Wazuh, Sysmon, and Auditd, enrichment strategies, MITRE mappings, and lab simulations to stress-test your detection logic.

## :dart: Why This Repo Exists

Anyone can collect logs. Anyone can trigger alerts.

But **real detection engineering** requires:

- Mapping behavior to telemetry
- Tuning rules to reduce false positives
- Enriching alerts with context
- Prioritizing signal over volume

This repo reflects that mindset: not just alerting — **precision signal engineering.**

## :mag: What's Covered

| Area                    | Description |
|-------------------------|-------------|
| `sigma-to-kql/`         | Converting Sigma rules into Azure KQL queries |
| `detection-logic/`      | Custom Wazuh, Sysmon, and auditd detection rules |
| `tuning-and-enrichment/`| Frameworks for reducing false positives and adding context |
| `mitre-mapping/`        | Each detection tied to real TTPs from MITRE ATT&CK |
| `detection-labs/`       | Simulated attack scenarios to test rule effectiveness |
| `dashboards/`           | Sample Kibana, Graylog, and Grafana visualizations |

## 📘 MITRE Technique Mapping

| TTP       | Description                        |
|----------|------------------------------------|
| T1003     | Credential Dumping (e.g., LSASS)   |
| T1059     | Command-Line Interface Abuse       |
| T1071.004 | Exfiltration Over DNS              |
| T1547     | Persistence via Startup Mechanisms |
| T1055     | Process Injection Techniques       |

## 🧪 Detection Labs Included

| Lab Scenario              | What You'll Learn                                     |
|--------------------------|-------------------------------------------------------|
| `brute-force-sim.md`      | Detect login failures with tuning for FP reduction    |
| `dns-tunneling-lab.md`    | Detect long query exfiltration over DNS               |
| `powershell-abuse-lab.md` | Detect encoded and obfuscated PowerShell execution    |
| `sysmon-trace-lab.md`     | Analyze process trees and command-line behavior       |
| `auditd-binary-exec.md`   | Detect Linux binary abuse using Auditd                |
| `atomic-redteam-setup.md` | Set up MITRE TTP simulations with Atomic Red Team     |

## 📊 Dashboards & Alert Visualizations

- **Kibana:** Alerts mapped to MITRE TTPs  
- **Graylog:** Stream tagging with detection logic context  
- **Grafana:** Volume visualization and tuning metrics  

## 👥 Who Should Use This

- Detection engineers tuning high-fidelity alerts  
- SOC analysts learning triage and prioritization  
- Blue teamers building MITRE-aligned detection coverage  
- Students and career switchers prepping for interviews  
- Security engineers refining telemetry-to-alert pipelines  



