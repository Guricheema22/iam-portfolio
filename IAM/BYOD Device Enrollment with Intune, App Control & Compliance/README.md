# Lab 02 – Microsoft Intune BYOD Enrollment & Application Management

## Overview
This lab demonstrates how Microsoft Intune is used to manage **Bring Your Own Device (BYOD)** access in an enterprise environment.

The objective is to show how an existing Microsoft Entra ID user enrolls a personal Windows device into Intune, gains controlled access to corporate applications, and is governed through centralized endpoint management — reflecting real-world enterprise endpoint security operations.

---

## Scenario
Employee **John Smith** uses his **personal Windows 11 Pro device** to access company applications and resources.

The administrator must:
- Enroll the personal device into Microsoft Intune
- Maintain BYOD ownership separation
- Control which applications are available to the user
- Verify device compliance and application visibility

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Intune
- Microsoft 365 Business Premium
- Windows 11 Pro (BYOD)
- Microsoft Company Portal

---

## Step-by-Step Implementation

### 1️⃣ BYOD Device Enrollment
- John Smith enrolled his personal Windows 11 device using **Microsoft Entra ID**
- Device joined through **Access work or school**
- Enrollment completed without converting the device to corporate-owned

📸 Evidence: `01-device-enrolled.png`

---

### 2️⃣ Device Visibility & Compliance
- Administrator verified device enrollment in Intune
- Confirmed:
  - Device appears under Windows devices
  - Ownership is marked as **Personal**
  - Device is managed by **Intune**
  - Compliance status is **Compliant**

📸 Evidence: `02-device-visible-intune.png`

---

### 3️⃣ Company Portal Access
- John Smith signed in to **Microsoft Company Portal**
- Verified successful authentication and device trust

📸 Evidence: `03-company-portal-login.png`

---

### 4️⃣ Application Visibility Validation
- Confirmed that the **Apps** section is accessible in Company Portal
- Validated that application catalog loads correctly for the user

📸 Evidence: `04-company-portal-apps-visible.png`

---

### 5️⃣ Application Assignment via Intune
- Administrator assigned approved applications via Intune
- Applications were assigned to **M365-Business-Users** security group
- Assignment type configured as **Available for enrolled devices**

📸 Evidence: `05-app-assignment-intune.png`

---

### 6️⃣ End-User Application Access
- John Smith verified assigned applications appear in Company Portal
- Confirmed only IT-approved applications are available for installation

📸 Evidence: `06-approved-apps-visible.png`

---

### 7️⃣ Configuration Profile Overview
- Administrator reviewed Windows configuration profiles in Intune
- Identified enterprise controls such as:
  - BitLocker encryption
  - Password policies
  - Device security settings

📸 Evidence: `07-configuration-profiles.png`

---

## Security & Endpoint Concepts Demonstrated
- BYOD device onboarding
- Separation of personal vs corporate ownership
- Centralized endpoint management
- Application allow-listing
- Group-based access control
- Endpoint compliance visibility

---

## Key Takeaways
- BYOD devices can be securely managed without full corporate ownership
- Intune provides centralized visibility and control over endpoints
- Application access can be tightly controlled using group assignments
- Company Portal acts as a secure bridge between users and corporate resources
- Endpoint management complements identity-first security models

---

## Next Lab
**Lab 03 – Conditional Access & Zero Trust Enforcement**

The next lab will focus on:
- Conditional Access policies
- MFA enforcement
- Device compliance conditions
- Zero Trust access decisions
