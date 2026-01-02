# 📘 Lab 02 – BYOD Device Enrollment with Intune, App Control & Compliance

## 📌 Lab Overview

In **Lab 01**, we created an end user (**John Smith**) and verified access by signing in through the end-user portal without enforcing any device controls.

In this lab, we move to a **real enterprise BYOD (Bring Your Own Device) scenario**, where:

> **John Smith accesses company applications from his personal Windows device**, and access is governed by **device enrollment, application control, and compliance policies**.

This lab focuses on **Microsoft Intune fundamentals** and establishes the foundation required for **Conditional Access**, which will be implemented in the next lab.

---

## 🎯 Lab Objectives

By the end of this lab, you will be able to:

- Enroll a **personal Windows 11 Pro device** into Intune  
- Use **group-based licensing** instead of direct user licensing  
- Control **which applications users are allowed to install**  
- Apply and evaluate **device compliance policies**  
- Validate device compliance from both admin and end-user perspectives  
- Collect **evidence** to prove enforcement  

> ⚠️ **Conditional Access is intentionally excluded** and will be covered in **Lab 03**.

---

## 🧱 Lab Architecture

| Component | Configuration |
|--------|--------------|
Identity Provider | Microsoft Entra ID |
Device Management | Microsoft Intune |
User | John Smith |
User Group | `M365-Business-Users` |
Licensing | Group-based |
Device Type | Personal Windows 11 Pro (BYOD) |
Security Scope | Device + Application Control |

---

## 👤 Phase 1 – Identity & Licensing (Enterprise Model)

### User Configuration
- **User:** John Smith  
- **Group Membership:**  
M365-Business-Users

csharp
Copy code

### Licensing Strategy
- Microsoft 365 Business Premium is assigned to:
M365-Business-Users

yaml
Copy code
- John Smith inherits the license automatically via group membership

**Why group-based licensing?**
- Scalable
- Auditable
- Enterprise best practice
- Reduces administrative overhead

---

## 💻 Phase 2 – Enrolling a Personal Device (BYOD)

### Scenario
John Smith uses his **personal Windows 11 Pro device** to access company applications.

### Enrollment Steps
On John Smith’s device:

1. Open  
Settings → Accounts → Access work or school

markdown
Copy code
2. Click **Connect**
3. Select  
Join this device to Microsoft Entra ID

yaml
Copy code
4. Sign in as **John Smith**
5. Complete setup and restart if prompted

---

### Enrollment Verification

Run the following command:

```cmd
dsregcmd /status
Expected output:

yaml
Copy code
IsDeviceJoined : YES
IsUserAzureAD  : YES
This confirms the device is Entra ID joined and Intune managed.

📱 Phase 3 – Company Portal Access
Open Company Portal

Sign in as John Smith

Confirm:

Device appears under Devices

Applications section is available

This validates successful Intune enrollment.

📦 Phase 4 – Application Control via Intune
Purpose
In enterprise environments:

Users are only allowed to install applications explicitly approved by IT.

This phase demonstrates application allow-listing using Intune.

App Assignment Steps
Navigate to:

nginx
Copy code
Intune → Apps → Windows
Select an application (e.g. Microsoft 365 Apps, Microsoft Edge, Store apps)

Open Assignments

Assign the app to:

Copy code
M365-Business-Users
Assignment Types
Required → Installs automatically

Available for enrolled devices → Visible in Company Portal

For this lab, apps are assigned as Available.

End-User Validation
On John Smith’s device:

Open Company Portal

Go to Apps

Confirm approved applications are visible and installable

🛡️ Phase 5 – Device Compliance Policy
Compliance Requirements
BitLocker enabled

Secure Boot enabled

Supported Windows version

Configuration Steps
Navigate to:

mathematica
Copy code
Intune → Devices → Windows → Compliance policies
Create a new policy for Windows 10 and later

Configure required security settings

Assign the policy to:

Copy code
M365-Business-Users
Compliance Validation
In Intune:

mathematica
Copy code
Devices → Windows → Windows devices
Confirm:

Device status is Compliant

This confirms the device meets organisational security requirements.
