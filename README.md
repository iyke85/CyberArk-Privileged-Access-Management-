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
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783513214766-a484555a-a803-4109-a04f-f9614f7c78a6.png)
![Architecture Diagram](https://www.image2url.com/r2/default/images/1783513286028-197195de-85a6-4779-9380-07884648b995.png)




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


## Conclusion

This lab gave me a clear, practical understanding of how CyberArk and Active Directory work together to protect privileged accounts in an enterprise environment. By creating the EndUser Engineering Safe, onboarding a Windows domain account, and assigning an AD group as a Safe member, I was able to see firsthand how organizations enforce least-privilege access — ensuring only the right people can access the right accounts at the right time.
This is one of the most fundamental skills in Privileged Access Management, and completing this lab has given me the confidence to replicate this process in a real-world environment.
