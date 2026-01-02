Lab 02 – Microsoft Intune BYOD Enrollment & Application Management
Overview

This lab demonstrates how Microsoft Intune is used to securely manage Bring Your Own Device (BYOD) access in an enterprise environment.

The objective is to showcase how an existing Microsoft Entra ID user enrolls a personal Windows device, gains controlled access to corporate applications, and is governed through centralized endpoint management — reflecting real-world enterprise device management practices.

Scenario

Employee John Smith uses his personal Windows 11 Pro device to access company resources and applications.

The organization must ensure:

The device is securely enrolled into Microsoft Intune

Corporate visibility and control are applied without full device ownership

Only IT-approved applications are available to the user

Technologies Used

Microsoft Entra ID

Microsoft Intune

Microsoft 365 Business Premium

Windows 11 Pro (BYOD)

Microsoft Company Portal

Prerequisites

User John Smith exists in Microsoft Entra ID

User is a member of M365-Business-Users group

Licenses are assigned via group-based licensing

Microsoft Intune is enabled in the tenant

Phase 1 – BYOD Device Enrollment
Objective

Enroll John Smith’s personal Windows device into Microsoft Intune using Entra ID, enabling secure access while maintaining BYOD separation.

Enrollment Steps (End User)

On John Smith’s personal Windows device:

Open Settings

Navigate to:
Settings → Accounts → Access work or school

Select Connect

Choose Join this device to Microsoft Entra ID

Sign in using John Smith’s Entra ID credentials

Complete setup and restart the device if prompted

Validation (Admin)

Open Intune Admin Center

Navigate to:
Devices → Windows

Confirm the device:

Appears in the device list

Is managed by Intune

Ownership is Personal

Compliance status shows Compliant

✅ This confirms successful BYOD enrollment.

Phase 2 – Company Portal Access
Objective

Validate that the enrolled device can access corporate resources via the Microsoft Company Portal.

Steps

Open Microsoft Company Portal

Sign in as John Smith

Navigate to the Apps section

Validation

Device appears under Devices

Applications section is available

Assigned corporate apps are visible

✅ This validates successful Intune enrollment and user-device trust.

Phase 3 – Application Control via Intune
Objective

Demonstrate application allow-listing where users can install only IT-approved applications.

App Assignment Steps (Admin)

Open Intune Admin Center

Navigate to:
Apps → All apps

Select an application (for example):

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

Assigned applications are visible

Installation is permitted

✅ Application access is successfully restricted and managed.

Phase 4 – Configuration Profiles Overview
Objective

Introduce device configuration profiles used to enforce enterprise security and system standards.

Navigation

Open Intune Admin Center

Navigate to:
Devices → Windows → Configuration

Create a new Configuration Profile

Select:

Platform: Windows 10 and later

Profile type: Settings catalog

Examples of Enterprise Controls

BitLocker drive encryption

Password and lock screen policies

Device security baselines

OS and system restrictions

Validation

Profile assigned to M365-Business-Users

Device reports successful policy application

Evidence Collection
Recommended Evidence

Device enrolled in Intune

Company Portal app visibility

App assignment configuration

Device compliance status
