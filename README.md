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


VMware Workstation Pro — Used to create and manage the virtual machines used in the lab.
Windows Server 2025 — Used as the domain controller and Active Directory server.
Active Directory Domain Services (AD DS) — Used for centralized user, computer, and group management.
Group Policy Management Console (GPMC) — Used to create, configure, and manage GPOs.
Windows Enterprise — Used as the domain-joined client system.
DNS — Used to allow the Windows client to locate and communicate with the Active Directory domain controller.
Command Prompt — Used to verify Group Policy changes.

## Steps
I first setup the Windows Server by getting an iso file from Microsoft.com and running it on a VM. I then installed the AD Domain services role and promoted the server to a domain controller. After this, I created OUs and structured them into 3 different locations. I applied group management by creating security and distribution groups. I also added user accounts into the created OUs. 


(Image 1: Showcases the Active Directory Users and Computers tab with Users, Security group, and Distribution group)
<img width="1019" height="661" alt="Screenshot 2026-08-10 143922" src="https://github.com/user-attachments/assets/0b1ce5de-1e63-41b2-aab7-a306c5847d1d" />


To create and configure Group Policy Objects (GPOs) in an Active Directory environment, the process went as follows. 

I make sure I have the Group Policy Management Console (GPMC) installed, and after ensuring its installed, I access it to view the domain and existing OUs. I then create different policies on the domain for different configurations. I determine whether the GPO will be used for Computer Configuration or User Configuration based on the goal of the policy and then apply it to that specific sector. I also differentiate based on if it will be a policy or preference.

(Image 2: Showcasing different policies for different purposes. Opened is the password security policies)
<img width="997" height="689" alt="Screenshot 2026-08-10 150855" src="https://github.com/user-attachments/assets/e702a9bf-19b2-4055-94e8-5566b24e1b0e" />


To finally apply and test the GPOs, I first set the domain controller with a static IP address and configure it as the primary DNS server. Then, I join the domain on a client machine by updating the DNS settings to point to the server. I use the Group Policy Management Console (GPMC) to assign the GPOs I made into the appropriate OUs such as putting the restrict control panel under users and password policy under computer. 

(Image 3: Showcasing the GPMC to assign created GPOs into right OUs)
<img width="836" height="736" alt="Screenshot 2026-08-10 162650" src="https://github.com/user-attachments/assets/871768c8-9148-48e3-9bce-8b83942f3c77" />

I assign the current client machine to a specific OU, so it has a specialized place and role, like in the USA Computers OU. 

I lastly test if the GPO is in effect by trying to open the Control Panel on the client machine. I verified its success as I am unable to on the client side, and also am requested to change my password when I signed back on.

## Results
The lab successfully demonstrated the deployment and configuration of an Active Directory environment using Windows Server 2025.

I configured a domain controller, Active Directory users and groups, Organizational Units, DNS, and multiple Group Policy Objects. I then joined a Windows client to the domain and tested the configured policies to verify that they were being successfully applied.

This project provided hands-on experience with Active Directory administration, domain controllers, DNS, user and group management, Organizational Units, Group Policy, domain joining, and GPO testing and troubleshooting.




