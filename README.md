# End-to-End Privileged Access Management Design and Deployment Using CyberArk
![Cloud Honeynet / SOC](https://i.imgur.com/NVGXgKA.png)

## Introduction
In this project, I set up and configured a CyberArk environment from scratch — creating Safes, onboarding privileged accounts, automating password rotation, recording and monitoring sessions, and generating compliance reports.
Every task in this project mirrors what PAM administrators do on the job every day, giving me real, practical experience that employers can see and verify.
![Architecture Diagram](https://www.image2url.com/r2/default/images/1782740867945-66741f18-b870-43c4-bdb1-86a5f03b6a3a.png)
## Active Directory Integration and Role-Based Access Control in CyberArk
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783411821504-1d4150e5-20ba-446b-99bd-ae85667a3aee.png)
In this lab, I built a complete access control workflow in CyberArk that integrates with Active Directory. I created a Safe called EndUser Engineering to store and protect the privileged account, onboarded a Windows domain account into a Windows Domain platform in CyberArk, created an AD security group also called EndUser Engineering, and assigned that group as a Safe member with the appropriate permissions. This mirrors exactly how enterprises manage privileged access at scale — using Safes to organise accounts and AD groups to control who can access them.
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783416278041-4a80a3a1-f17d-4fd3-8084-6372274a4390.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783416565730-21f9d832-3b82-41a8-a1a3-2d00e5a17cd3.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783416726419-a59413b3-fa2a-466c-b43b-338b64477463.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783416975047-ccbb1ca4-39f0-4202-ad6d-7f97bb5ac9c5.png)
# Account Onboarding
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783413890588-f8b1acef-dde3-4f01-9a62-6432eb83f80c.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783417427342-53f6ea61-2db4-46d4-b8f3-fffbd0fbefa2.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783417970674-2bd33410-883e-4f7f-b62f-dc1143e12b64.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783418146752-c3df56c7-293a-4542-a269-65187e829810.png)
![Architecture Diagram](https://i.imgur.com/aBDwnKb.jpg)
![Architecture Diagram](https://i.imgur.com/aBDwnKb.jpg)
![Architecture Diagram](https://i.imgur.com/aBDwnKb.jpg)
v


# Skills learned
- Safe creation and configuration in CyberArk
- Active Directory security group creation and management
- Privileged account onboarding into a Windows Domain platform
- Safe member configuration and permission assignment
- Role-based access control (RBAC) using AD groups
 # Business impact
In a real company, this setup means privileged accounts are stored securely inside a Safe, and only members of the right AD group can access them. Access can be granted or revoked instantly by updating the group — no need to touch CyberArk for each user individually. This reduces the risk of unauthorised access, supports audit compliance, and saves IT teams significant time managing access at scale.

# Tools and technologies

- CyberArk PVWA
- CyberArk Safe
- Active Directory
- Windows Domain Platform
- Safe Member Permissions
- RBAC




### Skills Learned
[Bullet Points - Remove this afterwards]


- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*


- SecurityEvent (Windows Event Logs)
- Syslog (Linux Event Logs)
- SecurityAlert (Log Analytics Alerts Triggered)
- SecurityIncident (Incidents created by Sentinel)
- AzureNetworkAnalytics_CL (Malicious Flows allowed into our honeynet)

## Architecture Before Hardening / Security Controls
![Architecture Diagram](https://i.imgur.com/aBDwnKb.jpg)

## Architecture After Hardening / Security Controls
![Architecture Diagram](https://i.imgur.com/YQNa9Pp.jpg)

The architecture of the mini honeynet in Azure consists of the following components:

- Virtual Network (VNet)
- Network Security Group (NSG)
- Virtual Machines (2 windows, 1 linux)
- Log Analytics Workspace
- Azure Key Vault
- Azure Storage Account
- Microsoft Sentinel

For the "BEFORE" metrics, all resources were originally deployed, exposed to the internet. The Virtual Machines had both their Network Security Groups and built-in firewalls wide open, and all other resources are deployed with public endpoints visible to the Internet; aka, no use for Private Endpoints.

For the "AFTER" metrics, Network Security Groups were hardened by blocking ALL traffic with the exception of my admin workstation, and all other resources were protected by their built-in firewalls as well as Private Endpoint

## Attack Maps Before Hardening / Security Controls
![NSG Allowed Inbound Malicious Flows](https://i.imgur.com/1qvswSX.png)<br>
![Linux Syslog Auth Failures](https://i.imgur.com/G1YgZt6.png)<br>
![Windows RDP/SMB Auth Failures](https://i.imgur.com/ESr9Dlv.png)<br>

## Metrics Before Hardening / Security Controls

The following table shows the metrics we measured in our insecure environment for 24 hours:
Start Time 2023-03-15 17:04:29
Stop Time 2023-03-16 17:04:29

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

The following table shows the metrics we measured in our environment for another 24 hours, but after we have applied security controls:
Start Time 2023-03-18 15:37
Stop Time	2023-03-19 15:37

| Metric                   | Count
| ------------------------ | -----
| SecurityEvent            | 8778
| Syslog                   | 25
| SecurityAlert            | 0
| SecurityIncident         | 0
| AzureNetworkAnalytics_CL | 0

## Conclusion

In this project, a mini honeynet was constructed in Microsoft Azure and log sources were integrated into a Log Analytics workspace. Microsoft Sentinel was employed to trigger alerts and create incidents based on the ingested logs. Additionally, metrics were measured in the insecure environment before security controls were applied, and then again after implementing security measures. It is noteworthy that the number of security events and incidents were drastically reduced after the security controls were applied, demonstrating their effectiveness.

It is worth noting that if the resources within the network were heavily utilized by regular users, it is likely that more security events and alerts may have been generated within the 24-hour period following the implementation of the security controls.
