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

* Departments: IT, Sales, Marketing (All under New York Site)
* Created OUs for each department
* Created groups for each department
* Created user accounts using naming convention (e.g., Jdoe)
* Configured user properties:
  * Password change at next login
  * Disabled on weekends

Screenshots included:

OU structure

Departmental groups

Users placed in correct OUs and groups

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

Department shares and access tests

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
