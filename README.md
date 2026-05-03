# Wazuh SIEM Home Lab – Brute Force Detection on Windows Endpoint

## Project Overview

This project demonstrates a cybersecurity home lab built using Wazuh SIEM, Ubuntu Server, and Windows 10 Virtual Machines in VirtualBox.

The main objective was to simulate failed login attempts (brute-force style authentication failures) and monitor them through Wazuh for detection, alert generation, and security event analysis.

This project helped me understand how Security Operations Center (SOC) workflows function in real environments, including endpoint monitoring, event analysis, agent deployment, and incident investigation.

---

## Lab Architecture

* Ubuntu 24.04 LTS → Wazuh Server (Manager)
* Windows 10 VM → Wazuh Agent (Endpoint)
* VirtualBox → Virtualization platform
* PowerShell → Agent installation and service management

### Detection Flow

Windows 10 Endpoint
↓
Failed Login Attempts
↓
Windows Security Event ID 4625
↓
Wazuh Agent collects logs
↓
Wazuh Server analyzes events
↓
Security Alert generated in Dashboard

---

## Technologies Used

* Wazuh SIEM
* Ubuntu Server
* Windows 10
* VirtualBox
* PowerShell
* Windows Event Viewer
* Security Event Logs
* Event ID 4625 Analysis

---

## Attack Simulation

To simulate suspicious authentication activity:

* Multiple failed login attempts were generated on the Windows 10 endpoint
* Incorrect username/password combinations were used
* Windows generated Security Event ID 4625
* Wazuh collected and analyzed these failed login events

This allowed detection of brute-force style authentication failures.

---

## Detection Analysis

### Event ID: 4625

This event indicates:

"An account failed to log on"

Key findings:

* Unknown username or bad password
* Authentication failure detected
* Logon Type: 2 (Interactive logon)
* Source process: svchost.exe
* Authentication package: Negotiate
* MITRE ATT&CK mapping included

Wazuh rule triggered:

Logon failure - Unknown user or bad password
Rule ID: 60122
Level: 5
MITRE: T1078, T1531

---

## Troubleshooting

During this project, several technical issues were solved:

* Wazuh agent disconnected after network change
* Ubuntu server IP changed after switching Wi-Fi networks
* Windows agent required reconfiguration due to new manager IP
* PowerShell required Administrator privileges for service management
* Never connected agents required cleanup and re-registration

These troubleshooting steps helped improve my understanding of real-world SOC operations and endpoint monitoring challenges.

---

## What I Learned

Through this project I learned:

* SIEM fundamentals
* Wazuh agent deployment
* Endpoint monitoring
* Windows Security Event analysis
* Failed login detection
* Event ID 4625 investigation
* Basic SOC analyst workflow
* Security alert triage and analysis

---

## Future Improvements

Future versions of this lab may include:

* Splunk integration
* Sysmon deployment
* Active Directory simulation
* More advanced brute-force scenarios
* Malware detection use cases
* Threat hunting workflows

---

## Screenshots

Screenshots of:

* Wazuh Dashboard
* Active Agents
* Security Events
* Event ID 4625 Detection
* PowerShell Agent Installation
* Ubuntu Wazuh Server

will be added to this repository.
