# Building a Secure Environment with Microsoft Azure

## Introduction
Introduction In this innovative project, I successfully built a robust Honeynet in Microsoft Azure that used real-time traffic analysis to improve security. By integrating logs from various sources into a log analysis workspace, we enable Microsoft Sentinel to generate insightful attack graphs, trigger alerts, and quickly respond to potential threats by generating events. To assess the effectiveness of security measures, I measured and compared key security indicators in an insecure environment before and after implementing strict security controls.

The indicators measured include:
1. Security Events (Windows Event Log)
2. Syslog (Linux Event Log)
3. SecurityAlert (triggers log analysis alert)
4.SecurityIncident (incident created by Sentinel)
5. AzureNetworkAnalytics_CL (to allow malicious traffic on our honey network)

## Architecture Before Hardening / Security Controls
![Architecture Diagram](https://i.imgur.com/aBDwnKb.jpg)
Architecture hardening: before and after hardening Before hardening: before security controls are applied The Azure Honeynet architecture consists of the following components:
• Virtual Network (VNet)
• Network Security Group (NSG)
• Virtual machines (2 Windows, 1 Linux)
• Log analysis workspace
• Azure Key Vault
• Azure storage account
• Microsoft Sentinel

## Attack Maps Before Hardening / Security Controls
![NSG Allowed Inbound Malicious Flows](https://i.imgur.com/1qvswSX.png)<br>
![Linux Syslog Auth Failures](https://i.imgur.com/G1YgZt6.png)<br>
![Windows RDP/SMB Auth Failures](https://i.imgur.com/ESr9Dlv.png)<br>

## Metrics Before Hardening / Security Controls   


| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 19470
| Syslog                   | 3028
| SecurityAlert            | 10
| SecurityIncident         | 348
| AzureNetworkAnalytics_CL | 843

## Attack Maps Before Hardening / Security Controls

```All map queries actually returned no results due to no instances of malicious activity for the 24 hour period after hardening.```

## Metrics After Hardening / Security Controls

Improved metrics: Measured for an additional 24 hours after the security check was implemented (start time: 2023-03-18 15:37, end time: 2023-03-19 15:37). The indicators achieved during this period show the positive impact of security control:

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 8778
| Syslog                   | 25
| SecurityAlert            | 0
| SecurityIncident         | 0
| AzureNetworkAnalytics_CL | 0

## Conclusion
Conclusion In summary, the project has successfully built a highly secure SOC + Honeynet in Microsoft Azure that uses real-time traffic analysis to proactively identify and respond to potential security threats. By integrating log sources into the Log Analytics workspace and using Microsoft Sentinel, we've achieved powerful alerting and event capabilities. The comparison of safety indicators before and after the introduction of safety control shows that there has been a significant reduction in safety incidents and incidents that confirm the effectiveness of the measures taken.
Note. It should be recognized that if the network resource is heavily used by regular users, a higher number of security events and alerts may be generated within 24 hours of the implementation of security controls

