# Lab 02 – Microsoft Intune BYOD Enrollment & Application Management

## Overview
This lab demonstrates how Microsoft Intune is used to securely manage Bring Your Own Device (BYOD) access in an enterprise environment.

The objective is to show how an existing Microsoft Entra ID user enrolls a personal Windows device, establishes device trust, and gains controlled access to corporate applications — reflecting real-world endpoint and identity integration practices.

---

## Scenario
Employee **John Smith** uses his personal Windows 11 Pro device to access corporate resources.

The organisation must:
- Securely enroll the personal device into Microsoft Intune
- Establish Microsoft Entra ID trust with the device
- Provide access only to IT-approved applications
- Maintain compliance visibility without full device ownership

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Intune
- Microsoft 365 Business Premium
- Windows 11 Pro (BYOD)
- Microsoft Company Portal
- Entra ID Device Management

---

## Implementation Steps

### 1. Device Join to Microsoft Entra ID
- Initiated **Join this device to Microsoft Entra ID** on a personal Windows 11 device
- Signed in using John Smith’s corporate account
- Device successfully registered and trusted by Entra ID

📸 Evidence: `01-entra-id-device-join.png`

---

### 2. Device Registration Confirmation
- Windows confirmed successful device registration
- Device identity established in Microsoft Entra ID

📸 Evidence: `02-device-registered-successfully.png`

---

### 3. Company Portal Sign-In
- Signed in to Microsoft Company Portal as John Smith
- Company Portal detected the enrolled BYOD device

📸 Evidence: `03-company-portal-signin.png`

---

### 4. Device Compliance Validation (End User View)
- Navigated to **Devices** section in Company Portal
- Device displayed a compliant status
- Confirmed device meets assigned security policies

📸 Evidence: `04-device-compliance-green-tick.png`

---

### 5. Application Visibility for User
- Navigated to **Apps** section in Company Portal
- Verified visibility of IT-approved applications only
- Confirms application allow-listing via Intune

📸 Evidence: `05-approved-apps-visible.png`

---

### 6. Administrative Verification in Intune
- Accessed Microsoft Intune Admin Center
- Verified device appears under Windows devices
- Device attributes confirmed:
  - Managed by Intune
  - Compliance status: Compliant
  - Ownership: Personal (BYOD)

📸 Evidence: `06-intune-device-visible.png`

---

### 7. Technical Validation – Entra ID Join Status
- Executed `dsregcmd /status` on the device
- Confirmed:
  - AzureAdJoined: YES
  - DeviceAuthStatus: SUCCESS
- Device successfully trusted by Microsoft Entra ID

📸 Evidence: `07-entra-id-join-validation.png`

---

## IAM & Endpoint Concepts Demonstrated
- BYOD enrollment using Microsoft Intune
- Microsoft Entra ID device trust establishment
- Separation of personal ownership and corporate control
- Application access governance
- Device compliance and posture visibility
- Identity-first endpoint security model

---

## Key Takeaways
- BYOD devices can securely access corporate resources without full device ownership
- Microsoft Entra ID provides strong device identity and trust
- Intune enables centralized endpoint visibility and control
- Application access is limited to IT-approved software
- Compliance can be validated from both user and administrator perspectives
