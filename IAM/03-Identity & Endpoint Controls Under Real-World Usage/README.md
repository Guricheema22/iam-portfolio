# Lab 03 – Identity & Endpoint Controls Under Real-World Usage

## Overview
This lab evaluates Microsoft Entra ID authentication behaviour during normal, day-to-day user activity.

Unlike previous labs that focus on configuration and onboarding, this lab is **observational**. The objective is to validate how identity, authentication, and endpoint controls behave once a user is already enrolled, licensed, and compliant — reflecting real-world enterprise usage rather than setup tasks.

---

## Scope
This lab assumes the following are already in place:
- **Lab 01** – Entra ID User, Group & License Lifecycle
- **Lab 02** – Intune BYOD Enrollment & Application Management

⚠️ No enrollment, configuration, or policy changes are performed in this lab.

---

## Scenario
Employee **John Smith** is actively using his Microsoft Entra ID account for daily work activities across Microsoft 365 services.

The organisation must ensure:
- Authentication remains seamless during normal usage
- Single Sign-On (SSO) functions correctly
- Identity activity is fully visible and auditable
- Security controls do not introduce unnecessary user friction

This lab aligns with real-world IAM guidance:

> **Security controls must be evaluated during daily usage, not only during initial setup.**

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Intune
- Microsoft 365 Business Premium
- Windows 11
- Microsoft 365 Applications
- Entra ID Sign-in Logs

---

## Objectives
- Observe authentication behaviour during normal user activity
- Validate Single Sign-On (SSO) across Microsoft 365 services
- Confirm visibility and auditability in Entra ID sign-in logs
- Ensure no unnecessary authentication prompts occur
- Establish a baseline enterprise authentication experience

---

## Validation Steps

### 1. Microsoft 365 Portal Access
- John Smith accesses the Microsoft 365 portal
- Portal loads successfully without requesting additional credentials
- Confirms valid authentication session and SSO behaviour

📸 Evidence: `01-m365-portal-access.png`

---

### 2. Microsoft 365 Application Access
- User opens Microsoft Word and Microsoft Teams
- Applications launch without additional sign-in prompts
- User identity is displayed within each application

📸 Evidence:
- `02-word-app-signed-in.png`
- `03-teams-app-access.png`

---

### 3. Entra ID Sign-In Log Verification
- Administrator reviews **Entra ID → Sign-in logs**
- Multiple successful sign-ins are recorded for:
  - OfficeHome
  - Azure Portal
  - Microsoft 365 applications
- All entries show:
  - Status: Success
  - Sign-in error code: 0
  - No authentication failures

📸 Evidence: `04-signin-logs-success.png`

---

## Observations & Analysis
- Single Sign-On (SSO) operates as expected
- Authentication tokens are reused across Microsoft services
- No repeated authentication challenges occur
- User experience remains seamless and uninterrupted
- Administrators retain full authentication visibility and audit capability

This behaviour represents a **correctly implemented enterprise identity baseline**.

---

## Key Takeaways
- Not every sign-in should trigger MFA
- Strong identity design balances security with usability
- SSO significantly improves end-user productivity
- Entra ID sign-in logs provide reliable audit and troubleshooting insights
- Establishing a baseline is critical before applying stricter Conditional Access controls

This lab sets the foundation for subsequent labs where authentication behaviour will be intentionally hardened using Conditional Access, MFA enforcement, and risk-based controls.
