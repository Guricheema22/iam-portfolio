Lab 02 – BYOD Device Enrollment with Intune, App Control & Compliance
📌 Lab Overview

In Lab 01, we created an end user (John Smith) and validated his access by signing in through the end-user portal without enforcing device controls.

In this lab, we move to a real enterprise BYOD (Bring Your Own Device) scenario, where:

John Smith accesses company applications from his personal Windows device, and access is governed by device enrollment, application control, and compliance policies.

This lab focuses on Microsoft Intune fundamentals and prepares the foundation for Conditional Access, which will be implemented in the next lab.

🎯 Lab Objectives

By the end of this lab, you will be able to:

Enroll a personal Windows 11 Pro device into Intune

Use group-based licensing instead of direct user licensing

Control which applications users are allowed to access

Apply and evaluate device compliance policies

Validate compliance status from both admin and end-user perspectives

Collect evidence to prove device and policy enforcement

⚠️ Conditional Access is intentionally excluded from this lab and will be covered in detail in Lab 03.

🧱 Lab Architecture
Component	Configuration
Identity Provider	Microsoft Entra ID
Device Management	Microsoft Intune
User	John Smith
User Group	M365-Business-Users
Licensing	Group-based
Device Type	Personal Windows 11 Pro (BYOD)
Security Scope	Device + App Control
👤 Phase 1 – Identity & Licensing (Enterprise Model)
User Configuration

User: John Smith

Group Membership:

M365-Business-Users

Licensing Strategy

Microsoft 365 Business Premium is assigned to:

M365-Business-Users


John Smith automatically receives the license via group membership

📌 Why group-based licensing?

Scalable

Auditable

Enterprise best practice

Minimises administrative overhead

💻 Phase 2 – Enrolling a Personal Device (BYOD)
Scenario

John Smith uses his personal Windows 11 Pro device to access corporate applications.

Enrollment Steps

On John Smith’s device:

Open

Settings → Accounts → Access work or school


Click Connect

Select

Join this device to Microsoft Entra ID


Sign in as John Smith

Complete setup and restart if prompted

Enrollment Verification

Run the following command:

dsregcmd /status


Expected output:

IsDeviceJoined : YES
IsUserAzureAD  : YES


This confirms the device is:

Entra ID joined

Managed by Intune

📱 Phase 3 – Company Portal Access

Open Company Portal

Sign in as John Smith

Confirm:

Device appears under Devices

Applications section is accessible

This validates successful Intune enrollment.

📦 Phase 4 – Application Control via Intune
Purpose

In enterprise environments:

Users are only allowed to install applications explicitly approved by IT.

This phase demonstrates application allow-listing using Intune.

App Assignment Steps

Navigate to:

Intune → Apps → Windows


Select an application (e.g. Microsoft 365 Apps, Edge, Store apps)

Open Assignments

Assign to:

M365-Business-Users

Assignment Types

Required → Automatically installed

Available for enrolled devices → Visible in Company Portal

📌 For this lab, applications are assigned as Available.

End-User Validation

On John Smith’s device:

Open Company Portal

Navigate to Apps

Confirm approved applications are visible and installable

🛡️ Phase 5 – Device Compliance Policy
Compliance Requirements

BitLocker enabled

Secure Boot enabled

Supported Windows version

Configuration Steps

Navigate to:

Intune → Devices → Windows → Compliance policies


Create a new policy for Windows 10 and later

Configure required security settings

Assign the policy to:

M365-Business-Users

Compliance Validation

In Intune:

Devices → Windows → Windows devices


Confirm:

Device status = Compliant

This confirms the device meets organisational security requirements.
