# ActiveDirectory & GPO Lab

## Objective
The objective of this lab was to build a Windows Active Directory home lab using VMware Workstation Pro and Windows Server 2025. The lab focused on deploying a domain controller, configuring Active Directory Domain Services, creating organizational units, users, and groups, and implementing Group Policy Objects (GPOs) to manage and enforce security and system settings across domain-joined systems.

The lab also included joining a Windows client to the domain and testing the configured Group Policy settings to verify that they were being successfully applied.

### Skills Learned


- Deployed and configured a Windows Server 2025 virtual machine.
- Installed and configured Active Directory Domain Services (AD DS).
- Promoted a Windows Server system to a domain controller.
- Configured and worked with Active Directory organizational units (OUs).
- Created and managed Active Directory users and security groups.
- Configured and managed Group Policy Objects (GPOs).
- Configured password and account security policies.
- Configured user and computer-based Group Policy settings.
- Joined a Windows client machine to an Active Directory domain.
- Applied and tested GPOs on a domain-joined Windows client.
- Troubleshot and verified Group Policy implementation.

### Tools Used

- VMware Workstation Pro — Virtualization platform used to host the Windows Server and Windows client virtual machines.
- Windows Server 2025 — Configured as the Active Directory Domain Services (AD DS) server and domain controller.
- Active Directory Domain Services (AD DS) — Used to manage domain users, groups, computers, and organizational units.
- Group Policy Management Console (GPMC) — Used to create, configure, and deploy Group Policy Objects (GPOs).
- Windows Enterprise Client — Domain-joined workstation used to test policy deployment and user management.
- DNS — Configured on the domain controller to provide Active Directory name resolution and domain service discovery.
- Command Prompt — Used to update and verify Group Policy deployment using administrative commands.

## Steps
I began by deploying a Windows Server 2025 virtual machine in VMware Workstation Pro using Microsoft's installation ISO. I then installed the AD Domain services role and promoted the server to a domain controller for a new Active Directory forest. I then designed an organizational structure by creating multiple Organizational Units (OUs), security groups, distribution groups, and user accounts to simulate a small business domain environment.


(Image 1: Showcases the Active Directory Users and Computers tab with Users, Security group, and Distribution group)
<img width="1019" height="661" alt="Screenshot 2026-08-10 143922" src="https://github.com/user-attachments/assets/0b1ce5de-1e63-41b2-aab7-a306c5847d1d" />


To create and configure Group Policy Objects (GPOs) in an Active Directory environment, the process went as follows. 

Using the Group Policy Management Console (GPMC), I created multiple Group Policy Objects to enforce domain security and user restrictions. Each GPO was configured under either Computer Configuration or User Configuration depending on whether the setting targeted computers or users. Policies included password security requirements, account policies, and restricting user access to the Windows Control Panel.

(Image 2: Showcasing different policies for different purposes. Opened is the password security policies)
<img width="997" height="689" alt="Screenshot 2026-08-10 150855" src="https://github.com/user-attachments/assets/e702a9bf-19b2-4055-94e8-5566b24e1b0e" />


To apply and test the GPOs, I configured the domain controller with a static IP address and configured the client machine to use the domain controller as its primary DNS server. I then joined the Windows client to the Active Directory domain. Using the Group Policy Management Console (GPMC), I linked the appropriate GPOs to their respective Organizational Units, including the Restrict Control Panel policy for users and computer-based policies for the appropriate computer OU.

(Image 3: Showcasing the GPMC to assign created GPOs into right OUs)
<img width="836" height="736" alt="Screenshot 2026-08-10 162650" src="https://github.com/user-attachments/assets/871768c8-9148-48e3-9bce-8b83942f3c77" />

The client computer account was moved into the USA Computers Organizational Unit to ensure it inherited the correct computer-based Group Policy Objects based on its organizational role.

Finally, I verified policy deployment by refreshing Group Policy on the client and testing the configured restrictions. The Control Panel was successfully blocked, and the client was prompted to change its password in accordance with the configured password policy, confirming that the GPOs were applied correctly.

### Verification

I verified successful Group Policy deployment using the `gpresult /r` command on the domain-joined Windows client. The output confirmed that the **Drive Mapping, Desktop Wallpaper, and Restrict Control Panel** GPOs were successfully applied to the logged-in user.

(Image 4: Using `gpresult /r` to verify that the configured Group Policy Objects were successfully applied to the domain-joined Windows client.)

<img width="722" height="764" alt="Screenshot 2026-08-13 140639" src="https://github.com/user-attachments/assets/08368cb0-3b8d-44bd-96a9-52882b3afd44" />


## Results
The lab successfully demonstrated the deployment and configuration of an Active Directory environment using Windows Server 2025.

I configured a domain controller, Active Directory users and groups, Organizational Units, DNS, and multiple Group Policy Objects. I then joined a Windows client to the domain and tested the configured policies to verify that they were being successfully applied.

This lab demonstrates practical experience deploying and administering a Windows Active Directory environment. It includes domain controller deployment, DNS configuration, Organizational Unit design, user and group administration, Group Policy management, domain joining, policy verification, and troubleshooting within a virtual enterprise network.



