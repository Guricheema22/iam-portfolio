# Lab 03 – Identity & Endpoint Controls Under Real-World Usage

## Overview
This lab evaluates Microsoft Entra ID authentication behaviour under normal, day-to-day user activity.

Unlike previous labs that focus on configuration and onboarding, this lab is observational. The goal is to validate how identity, authentication, and endpoint controls behave once a user is already enrolled and licensed — reflecting real-world enterprise usage rather than setup tasks.

---

## Scope
This lab assumes the following are already in place:

- Lab 01 – Entra ID User, Group & License Lifecycle
- Lab 02 – Intune BYOD Enrollment & Application Management

⚠️ No enrollment, configuration, or policy changes are performed in this lab.

---

## Scenario
**John Smith** now uses his Microsoft Entra ID account for daily work activities.

The objective is to observe how identity, authentication, and endpoint controls function during normal usage, without forcing additional security prompts or user friction.

This lab follows real-world IAM guidance:

> *Security controls must be evaluated in daily usage, not only during setup.*

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
- Validate expected enterprise authentication behaviour

---

## Validation Steps

### 1️⃣ Microsoft 365 Portal Access
- John Smith accesses the Microsoft 365 portal
- Portal loads successfully without requesting additional credentials
- Confirms valid authentication session and SSO behaviour

📸 Evidence: `01-m365-portal-access.png`

---

### 2️⃣ Microsoft 365 Application Access
- User opens Microsoft Word and Microsoft Teams
- Applications launch without additional sign-in prompts
- User identity is displayed within applications

📸 Evidence:
- `02-word-app-signed-in.png`
- `03-teams-app-access.png`

---

### 3️⃣ Sign-In Log Verification
- Administrator reviews **Entra ID → Sign-in logs**
- Multiple successful sign-ins are recorded for:
  - OfficeHome
  - Azure Portal
  - Microsoft 365 applications
- All entries show:
  - Status: **Success**
  - Sign-in error code: **0**
  - No authentication failures

📸 Evidence: `04-signin-logs-success.png`

---

## Observations & Analysis
- Single Sign-On (SSO) functions as expected
- Authentication tokens are reused across Microsoft services
- No repeated authentication challenges occur
- User experience remains seamless
- Administrators retain full audit visibility

This behaviour represents a correctly implemented enterprise identity baseline.

---

## Key Takeaways
- Not every sign-in should trigger MFA
- Strong identity design balances security and usability
- SSO significantly improves productivity
- Entra ID sign-in logs provide reliable validation and audit capability

This lab establishes a baseline authentication experience that will be hardened in subsequent labs using Conditional Access and MFA policies.

---

## Evidence Folder Structure
