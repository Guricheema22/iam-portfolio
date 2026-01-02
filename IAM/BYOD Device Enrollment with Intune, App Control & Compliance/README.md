📌 Lab Overview

This lab demonstrates how an enterprise organization uses Microsoft Entra ID and Microsoft Intune to manage identities, devices, and applications using modern Zero Trust principles.

The lab is split into multiple phases to reflect how these controls are introduced in real-world environments.

Important Design Choice

Conditional Access is intentionally excluded from this lab

Conditional Access will be implemented in the next dedicated lab for clarity and depth

🏗 Environment Details

Tenant: Microsoft Entra ID (Azure AD)

MDM: Microsoft Intune

Device Type: Windows 11 Pro (BYOD)

User: John Smith

License Model: Group-based licensing

User Group: M365-Business-Users

Phase 1 – Identity Creation & Baseline Access Validation
Scenario

The organization creates a new employee account and validates that identity authentication works correctly before allowing device enrollment or application access.

Steps

Create user John Smith in Microsoft Entra ID

Add John Smith to the group:

M365-Business-Users

Assign licenses to the group, not the user:

Microsoft 365 Business Premium

Microsoft Intune

Verify John Smith can sign in to:

Microsoft Entra end-user portal

Validation

User authentication is successful

Licenses are inherited via group membership

No devices are enrolled at this stage

✅ Identity is confirmed and ready for device onboarding

Phase 2 – Enrolling a Personal Device (BYOD)
Scenario

John Smith uses his personal Windows 11 Pro device to access company resources.
Microsoft Intune is introduced to securely manage the device without taking full ownership.

Objectives

Enroll a personal device into Intune

Register the device with Microsoft Entra ID

Validate device compliance and visibility

Enrollment Steps (On John Smith’s Device)

Open Settings

Navigate to:
Settings → Accounts → Access work or school

Select Connect

Choose Join this device to Microsoft Entra ID

Sign in as John Smith

Complete enrollment and restart if prompted

Admin Validation

Open Intune Admin Center

Navigate to:
Devices → Windows

Confirm:

Device is listed

Managed by: Intune

Ownership: Personal

Compliance status: Compliant

✅ Device enrollment completed successfully

Phase 3 – Company Portal Access
Purpose

The Company Portal is the user-facing application that allows employees to:

View approved applications

Install corporate software

Check device compliance

Steps (End User)

Open Company Portal

Sign in as John Smith

Navigate to the Apps section

Expected Outcome

Device appears under Devices

Apps tab is available

Company-approved applications are visible

✅ Confirms successful Intune enrollment and user-device trust

Phase 4 – Application Control via Intune
Purpose

Enterprise environments restrict software installation to approved applications only.

This phase demonstrates how Intune controls which apps users can access.

App Assignment (Admin Side)

Open Intune Admin Center

Navigate to:
Apps → All apps

Select an application (example):

Microsoft 365 Apps for Windows

Microsoft Edge

Open Assignments

Assign the app to:

M365-Business-Users group

Choose assignment type:

Available for enrolled devices or Required

Save the configuration

End-User Validation

Open Company Portal

Navigate to Apps

Confirm:

Assigned applications are visible

Installation is allowed

✅ Application allow-listing enforced successfully

Phase 5 – Configuration Profiles (Device Controls)
Purpose

Configuration profiles allow IT to enforce security and system settings on enrolled devices.

Navigation

Open Intune Admin Center

Navigate to:
Devices → Windows → Configuration

Create a new Configuration Profile

Select:

Platform: Windows 10 and later

Profile type: (e.g., Settings catalog)

Examples of Controls

BitLocker enforcement

Password policies

OS security baselines

Device restrictions

Validation

Profile assigned to M365-Business-Users

Device reports successful configuration status
