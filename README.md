# Windows Server Active Directory Lab
This project demonstrates a full Active Directory Domain Services (AD DS) deployment in a virtualized lab environment for a fictional company. The setup includes user/group management, Group Policy Objects (GPOs), shared resources, roaming profiles, and secure network configurations.

## Table of Contents

* Objectives
* Tools Used
* Network Topology
* Part 1: Create Users, Groups, and OUs
* Part 2: Setup Resources and Profiles
* Part 3: Group Policy Configuration
* Part 4: Questions & Reflection


## Objectives

* Create users, groups, and OUs per department.
* Configure shared folders, home folders, and roaming profiles.
* Apply GPOs for role-based access.

## Network Topology

Subnet: 10.0.0.0/24
Network Mode: NATNetwork (DHCP disabled)


## Tools Used

* VirtualBox
* Windows Server 2019
* Windows 10
* Active Directory Domain Services (AD DS)
* DHCP, DNS, WDS
* Group Policy Management Console (GPMC)

## Part 1: Create Users, Groups, and OUs

* Departments: IT, Sales, Marketing
* Created OUs for each department
* Created security groups for each department
* Created user accounts using naming convention (e.g., Jdoe)
* Configured user properties:
  * Password change at next login
  * Disabled on weekends

Screenshots included:

OU structure

  <img width="175" height="93" alt="image" src="https://github.com/user-attachments/assets/f46d3469-918f-4dad-b734-b6ceec65ea13" />


Departmental security groups
* IT security group

  <img width="800" height="483" alt="image" src="https://github.com/user-attachments/assets/ae35df5e-6004-4c9f-a77a-2d98c2215e74" />

* Sales security group

  <img width="801" height="480" alt="image" src="https://github.com/user-attachments/assets/48a78796-54aa-4a06-9f56-93c17e1e03b8" />

* Marketing security group

  <img width="813" height="489" alt="image" src="https://github.com/user-attachments/assets/2e60b98b-8fbd-4168-87f7-c353ae3e3259" />


Users placed in OUs and groups

* IT

  <img width="802" height="480" alt="image" src="https://github.com/user-attachments/assets/b3f8095c-a502-45f6-9472-daff8bc0de40" />

* Sales

  <img width="803" height="481" alt="image" src="https://github.com/user-attachments/assets/0129e389-98af-47cf-bbfa-b8ce1a90e3be" />

* Marketing

  <img width="802" height="482" alt="image" src="https://github.com/user-attachments/assets/b1944efa-76a4-4217-a919-b4eb93a50476" />


## Part 2: Setup Resources and Profiles

a) Shared Drives
* Created department-specific shares: ITShare, SalesShare, MarketingShare
* Applied NTFS and share permissions

b) Home Folders
* Created personal home folders for each user
* Assigned folder path via AD user properties

c) Roaming Profiles
* Created profile share path (e.g., \\MS-DC01\Profiles\Jdoe)
* Configured user profile paths
* Verified permissions

Screenshots included:

Department shares and sharing permissions
* IT
  
  <img width="544" height="92" alt="image" src="https://github.com/user-attachments/assets/403e14ea-d4de-453b-b0e7-d95ebc7a1bed" />
  <img width="924" height="391" alt="image" src="https://github.com/user-attachments/assets/1f02bd13-b18a-4c1f-9d6c-094bc880b3bc" />

* Sales
  
  <img width="527" height="95" alt="image" src="https://github.com/user-attachments/assets/55e56a96-6536-41e8-b12f-eb7165835daf" />
  <img width="912" height="301" alt="image" src="https://github.com/user-attachments/assets/3c32a298-4f5b-4563-92b0-7acfd5c8cbd5" />

* Marketing
  
  <img width="547" height="68" alt="image" src="https://github.com/user-attachments/assets/5e0bce58-3a7f-44c2-aceb-09ea81f034ca" />
  <img width="910" height="391" alt="image" src="https://github.com/user-attachments/assets/ba2d0bcc-bb53-4342-acd2-c79ddf84f005" />


NTFS permissions

Home folder creation

Roaming profile configuration

## Part 3: Group Policy Configuration

Mapped Network Drives GPOs
* Created GPOs for each department to map shared drives
* Linked GPOs to relevant groups

Access Restrictions (Sales & Marketing)
* Created GPOs to:
* Disable Control Panel (Sales & Marketing)
* Block Task Manager (Marketing)
* Deny CMD (Sales)
