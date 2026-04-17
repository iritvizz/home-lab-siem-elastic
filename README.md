# Home Lab SIEM Setup & Log Analysis

A personal Security Information and Event Management (SIEM) environment built using **Elastic Stack** to ingest, visualize, and detect security events from Windows and Linux systems.

## Project Overview
- Built a fully functional SIEM using **Elastic Cloud Hosted** + **Elastic Agents**.
- Ingested security logs from **Windows 10** and **Kali Linux** VMs.
- Created custom dashboards for log analysis.
- Configured brute-force detection alerts.
- Analyzed 50+ sample security events and documented the triage process.

## Architecture
- **SIEM Platform**: Elastic Cloud Hosted (v9.3.3)
- **Log Shippers**: Elastic Agent (System + Windows + Custom Logs integrations)
- **Hosts**:
  - Windows 10 VM (Security Event Logs)
  - Kali Linux VM (System & auth logs)

## Key Features Implemented

### Custom Dashboards
- Failed logins over time
- Top failed login source IPs
- Events by host
- Real-time visualization of brute-force activity

### Detection Rules
- Enabled **Brute Force Attempts** detection rule
- Threshold-based alerting (5+ failed attempts from same source IP in 5 minutes)
- Generated and triggered 7+ high-severity alerts

### Sample Events Generated
- 50+ failed login attempts (Windows Event ID 4625 + SSH failures)
- Brute-force simulation using loops on both Windows and Linux

## Triage Process
See [`Triage_Process.md`](Triage_Process.md) for detailed analysis and screenshots.

## Screenshots
*(Add your screenshots here in a `/screenshots` folder)*

- Custom Dashboard - Security Overview
- Brute Force Alerts (7 alerts triggered)
- Alert Investigation View
- Fleet Agents Status (Healthy)

## Lessons Learned
- Proper log ingestion differs significantly between Windows and Linux (Windows logs are better normalized).
- Custom Filestream integration is useful when default System integration doesn't capture auth failures well on Kali.
- Threshold rules need proper tuning (group by `source.ip`) to avoid noise.
- Real-world triage involves distinguishing test/lab traffic from actual threats.

## Technologies Used
- Elastic Stack (Elasticsearch, Kibana, Elastic Agent)
- Elastic Cloud Hosted
- Windows Event Logs + Linux auth logs
- KQL (Kibana Query Language)

## GitHub Repository
This entire project documentation + screenshots.

---

**Resume Bullet Points (Ready to Copy):**

- Built a personal SIEM environment using Elastic Stack to ingest and analyze Windows and Linux security logs.
- Created custom Kibana dashboards and enabled brute-force detection rules to identify anomalous login attempts.
- Generated and analyzed 50+ sample security events; documented full triage process for brute-force alerts.
- Gained hands-on experience with log ingestion, visualization, alerting, and incident triage in a home lab setup.
