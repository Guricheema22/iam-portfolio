# Lab 02 – Microsoft Intune BYOD Enrollment & Application Management

## Overview
This lab demonstrates how Microsoft Intune is used to securely manage Bring Your Own Device (BYOD) access in an enterprise environment.

The objective is to show how an existing Microsoft Entra ID user enrolls a personal Windows device, gains controlled access to corporate applications via Intune, and how device trust and compliance are validated — reflecting real-world enterprise endpoint management practices.

---

## Scenario
Employee **John Smith** uses his personal **Windows 11 Pro** device to access company resources and applications.

The organisation must:
- Securely enroll the personal device into Microsoft Intune
- Establish Microsoft Entra ID trust with the device
- Provide access only to IT-approved applications
- Maintain visibility of device compliance without full device ownership

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Intune
- Microsoft 365 Business Premium
- Windows 11 Pro (BYOD)
- Microsoft Company Portal
- Microsoft Entra ID Device Management

---

## Step-by-Step Implementation

### 1️⃣ Join Device to Microsoft Entra ID
- On the personal Windows 11 device, initiated **Join this device to Microsoft Entra ID**
- Signed in using **John Smith’s work account**
- Device successfully registered and trusted by Entra ID

📸 Evidence: `01-entra-id-device-join.png`

---

### 2️⃣ Device Registration Confirmation
- Windows confirmed successful registration of the device
- Device identity established with Microsoft Entra ID

📸 Evidence: `02-device-registered-successfully.png`

---

### 3️⃣ Company Portal Sign-In
- Signed in to **Microsoft Company Portal** as John Smith
- Company Portal recognized the enrolled device

📸 Evidence: `03-company-portal-signin.png`

---

### 4️⃣ Device Compliance Validation (End User View)
- Navigated to **Devices** tab in Company Portal
- Device showed **green compliance status**
- Confirmed device meets assigned security and compliance policies

📸 Evidence: `04-device-compliance-green-tick.png`

---

### 5️⃣ Application Visibility for User
- Navigated to **Apps** section in Company Portal
- Verified visibility of **IT-approved applications only**
- Confirms application allow-listing via Intune

📸 Evidence: `05-approved-apps-visible.png`

---

### 6️⃣ Administrative Verification in Intune
- Accessed **Microsoft Intune Admin Center**
- Verified device appears under **Windows devices**
- Device status shows:
  - Managed by Intune
  - Compliance = Compliant
  - Ownership = Personal (BYOD)

📸 Evidence: `06-intune-device-visible.png`

---

### 7️⃣ Technical Validation – Entra ID Join Status
- Executed `dsregcmd /status` on the device
- Confirmed:
  - `AzureAdJoined : YES`
  - `DeviceAuthStatus : SUCCESS`
  - Device successfully trusted by Microsoft Entra ID

📸 Evidence: `07-entra-id-join-validation.png`

---

## Security & Endpoint Management Concepts Demonstrated
- BYOD enrollment using Microsoft Intune
- Microsoft Entra ID device trust establishment
- Separation of personal ownership and corporate control
- Application access governance via Intune
- Device compliance and posture visibility
- Identity-first endpoint security model

---

## Key Takeaways
- BYOD devices can securely access corporate resources without full device ownership
- Microsoft Entra ID provides strong device identity and trust
- Intune enables centralized visibility and application control
- Users only see applications explicitly approved by IT
- Device compliance can be verified from both user and admin perspectives

---
