Lab 02 – Microsoft Intune BYOD Enrollment & Application Management
Overview

This lab demonstrates how Microsoft Intune is used to securely manage Bring Your Own Device (BYOD) scenarios in an enterprise environment.

The objective is to show how a previously created Entra ID user is onboarded with a personal Windows device, enrolled into Intune, provided controlled access to corporate applications, and validated through device and application visibility — reflecting real-world endpoint management practices.

Scenario

Employee John Smith uses his personal Windows 11 Pro device to access company resources.

The organization must ensure that:

The device is securely enrolled into Microsoft Intune

Corporate visibility and control are enforced without full device ownership

Only approved applications are accessible to the user

Technologies Used

Microsoft Entra ID

Microsoft Intune

Microsoft 365 Business Premium

Windows 11 Pro (BYOD)

Microsoft Company Portal

Prerequisites

User John Smith already exists in Microsoft Entra ID

User is a member of the M365-Business-Users group

Licenses are assigned via group-based licensing

Microsoft Intune is enabled for the tenant

Phase 1 – BYOD Device Enrollment
Objective

Enroll John Smith’s personal Windows device into Intune using Microsoft Entra ID, enabling device management without converting it to a corporate-owned asset.

Enrollment Steps (End User)

On John Smith’s personal device:

Open Settings

Navigate to:
Settings → Accounts → Access work or school

Select Connect

Choose Join this device to Microsoft Entra ID

Sign in using John Smith’s Entra ID credentials

Complete setup and restart if prompted

Validation (Admin)

Open Intune Admin Center

Navigate to:
Devices → Windows

Confirm the device:

Appears in the device list

Is managed by Intune

Shows ownership as Personal

Reports Compliant status

✅ This confirms successful BYOD enrollment.

Phase 2 – Company Portal Access
Objective

Validate that the enrolled device can access corporate resources through the Microsoft Company Portal.

Steps

Open Company Portal on the enrolled device

Sign in as John Smith

Navigate to the Apps section

Validation

Device is visible under Devices

Apps section is accessible

Corporate applications are listed

✅ This validates successful Intune enrollment and user-device trust.

Phase 3 – Application Control via Intune
Objective

Demonstrate how enterprises restrict application access by allowing users to install only approved applications.

App Assignment Steps (Admin)

Open Intune Admin Center

Navigate to:
Apps → All apps

Select an application (example):

Microsoft 365 Apps for Windows

Microsoft Edge

Open Assignments

Assign the app to:

M365-Business-Users group

Set assignment type:

Available for enrolled devices or Required

Save the configuration

End-User Validation

Open Company Portal

Navigate to Apps

Confirm:

Assigned apps are visible

Installation is permitted

✅ Application allow-listing is successfully enforced.

Phase 4 – Configuration Profiles Overview
Objective

Introduce device configuration profiles used to enforce security and system settings in enterprise environments.

Navigation

Open Intune Admin Center

Navigate to:
Devices → Windows → Configuration

Create a new Configuration Profile

Select:

Platform: Windows 10 and later

Profile type: Settings catalog

Examples of Enterprise Controls

BitLocker enforcement

Password and lock screen policies

Device security baselines

OS configuration restrictions

Validation

Profile assigned to M365-Business-Users

Device reports successful configuration deployment
