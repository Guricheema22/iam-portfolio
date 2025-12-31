# Lab 01 – Microsoft Entra ID User, Group & License Lifecycle

## Overview
This lab demonstrates an end-to-end Identity and Access Management (IAM) workflow using Microsoft Entra ID and Microsoft 365.

The objective is to show how a user is created, governed through group-based licensing, securely onboarded with MFA, and verified through sign-in logs — reflecting real-world enterprise IAM operations.

---

## Scenario
A new employee **John Smith** joins the organisation and requires access to Microsoft 365 services.

The administrator must:
- Create the user
- Assign licenses via a security group
- Enforce secure first-time sign-in
- Verify access and authentication activity

---

## Technologies Used
- Microsoft Entra ID
- Microsoft 365 Admin Center
- Azure Active Directory Premium P1
- MFA (Microsoft Authenticator)
- Entra ID Sign-in Logs

---

## Step-by-Step Implementation

### 1️⃣ User Creation
- Created a new cloud user **John Smith** in Microsoft Entra ID
- Configured user with initial password and forced password change on first login

📸 Evidence: `01-user-created.png`

---

### 2️⃣ Group Creation
- Created a security group **M365-Users**
- Group used for license-based access management

📸 Evidence: `02-group-created.png`

---

### 3️⃣ Group-Based License Assignment
- Assigned **Microsoft 365 Business Standard** license to the group
- Verified license inheritance at user level

📸 Evidence:  
- `03-license-assigned.png`

---

### 4️⃣ First-Time User Login
- User signed in for the first time using provided credentials
- Prompted to reset password

📸 Evidence: `04-first-login-password-reset.png`

---

### 5️⃣ MFA Registration
- User completed MFA registration using Microsoft Authenticator
- MFA successfully enforced during sign-in

📸 Evidence: `05-mfa-setup.png`

---

### 6️⃣ User Access Validation
- User successfully accessed Microsoft 365 portal
- Verified availability of:
  - Outlook
  - Microsoft 365 apps dashboard

📸 Evidence:  
- `06-m365-dashboard.png`  
- `07-outlook-working.png`

---

### 7️⃣ Administrative Verification
- Administrator reviewed **Entra ID sign-in logs**
- Confirmed successful authentication, MFA status, and access details

📸 Evidence: `08-signin-logs.png`

---

## Security & IAM Concepts Demonstrated
- Identity lifecycle management
- Group-based licensing
- Least privilege access
- MFA enforcement
- Audit and sign-in monitoring
- Identity-first security design

---

## Key Takeaways
- Group-based licensing simplifies access management
- MFA is enforced automatically without manual intervention
- Sign-in logs provide strong audit and troubleshooting capabilities
- Identity controls are simple to manage but significantly improve security

---


