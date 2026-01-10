# Lab 01 – Microsoft Entra ID User, Group & License Lifecycle

## Overview
This lab demonstrates an end-to-end Identity and Access Management (IAM) workflow using Microsoft Entra ID and Microsoft 365.

The objective is to show how a user identity is created, governed through group-based licensing, securely onboarded with MFA, and validated through sign-in activity — reflecting real-world IAM operations.

---

## Scenario
A new employee **John Smith** joins the organisation and requires access to Microsoft 365 services.

The administrator must:
- Create the user identity
- Assign licenses via a security group
- Enforce secure first-time sign-in
- Verify authentication and access activity

---

## Technologies Used
- Microsoft Entra ID
- Microsoft 365 Admin Center
- Azure Active Directory Premium P1
- MFA (Microsoft Authenticator)
- Entra ID Sign-in Logs

---

## Implementation Steps

### 1. User Creation
- Created a new cloud user **John Smith** in Microsoft Entra ID
- Configured an initial password with forced password change on first login

📸 Evidence: `01-user-created.png`

---

### 2. Security Group Creation
- Created a security group **M365-Users**
- Group designed for centralized license management

📸 Evidence: `02-group-created.png`

---

### 3. Group-Based License Assignment
- Assigned **Microsoft 365 Business Standard** license to the group
- Verified license inheritance at the user level

📸 Evidence: `03-license-assigned.png`

---

### 4. First-Time User Sign-In
- User signed in using initial credentials
- Password reset enforced at first login

📸 Evidence: `04-first-login-password-reset.png`

---

### 5. MFA Registration
- User registered Microsoft Authenticator
- MFA successfully enforced during authentication

📸 Evidence: `05-mfa-setup.png`

---

### 6. Access Validation
- User successfully accessed Microsoft 365 portal
- Verified access to:
  - Microsoft 365 dashboard
  - Outlook

📸 Evidence:
- `06-m365-dashboard.png`
- `07-outlook-working.png`

---

### 7. Administrative Verification
- Reviewed Entra ID sign-in logs
- Confirmed successful authentication and MFA status

📸 Evidence: `08-signin-logs.png`

---

## IAM Concepts Demonstrated
- Joiner lifecycle management
- Group-based licensing
- Least privilege access
- MFA enforcement
- Identity audit and monitoring

---

## Key Takeaways
- Group-based licensing simplifies access governance
- MFA strengthens authentication without manual enforcement
- Sign-in logs provide visibility for audit and troubleshooting
- Identity controls scale effectively in enterprise environments
