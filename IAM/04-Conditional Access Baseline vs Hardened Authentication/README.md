# Lab 04 – Conditional Access Baseline vs Hardened Authentication

## Overview
This lab demonstrates how Microsoft Entra ID Conditional Access policies are used to control authentication behaviour based on risk, device state, and access context.

The objective is to establish a **baseline Conditional Access policy**, observe its behaviour during real-world usage, and then **harden the policy** to increase security while maintaining usability.

This reflects how Conditional Access is implemented and iteratively refined in enterprise environments.

---

## Scope
This lab builds on the following completed labs:
- **Lab 01** – Entra ID User, Group & License Lifecycle
- **Lab 02** – Intune BYOD Enrollment & Application Management
- **Lab 03** – Identity & Endpoint Controls Under Real-World Usage

The user is already:
- Licensed
- MFA registered
- Using a compliant Windows 11 device
- Actively accessing Microsoft 365 services

---

## Scenario
Employee **John Smith** accesses Microsoft 365 services from a compliant, Intune-enrolled personal device.

The organisation wants to:
- Enforce MFA using Conditional Access
- Ensure trusted, compliant devices are prioritised
- Reduce unnecessary MFA prompts
- Maintain audit visibility and control

This lab follows real-world IAM best practice:

> **Conditional Access should be risk-aware, not disruptive.**

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Entra Conditional Access
- Microsoft Intune
- Microsoft 365 Business Premium
- Windows 11
- Microsoft Authenticator
- Entra ID Sign-in Logs

---

## Objectives
- Create a baseline Conditional Access policy
- Validate authentication behaviour under normal conditions
- Harden Conditional Access rules to improve security posture
- Observe the impact on user experience and sign-in logs
- Understand why MFA does or does not trigger

---

## Implementation & Validation

### 1️⃣ Baseline Conditional Access Policy (MFA Enforcement)
- Created a Conditional Access policy:
  - Users: John Smith
  - Cloud apps: Microsoft 365
  - Grant controls: Require MFA
- Policy set to **Report-only** initially
- Verified no immediate disruption to user access

📸 Evidence: `01-ca-policy-baseline.png`

---

### 2️⃣ Authentication Behaviour Validation
- John Smith accesses Microsoft 365 portal
- No MFA prompt occurs due to existing valid authentication session
- Demonstrates token reuse and SSO behaviour

📸 Evidence: `02-m365-access-no-mfa.png`

---

### 3️⃣ Sign-In Log Analysis (Baseline)
- Reviewed Entra ID sign-in logs
- Conditional Access tab shows:
  - Policy evaluated
  - Result: Not Applied / Satisfied
- Confirms Conditional Access logic is functioning correctly

📸 Evidence: `03-signin-logs-baseline-ca.png`

---

### 4️⃣ Conditional Access Hardening
- Updated Conditional Access policy:
  - Require MFA **AND** compliant device
  - Block access from non-compliant devices
- Policy moved from Report-only to **On**

📸 Evidence: `04-ca-policy-hardened.png`

---

### 5️⃣ Post-Hardening Validation
- John Smith accesses Microsoft 365 from compliant device
- Access succeeds without additional prompts
- Demonstrates strong security with minimal user friction

📸 Evidence: `05-m365-access-compliant-device.png`

---

### 6️⃣ Administrative Verification
- Reviewed Entra ID sign-in logs
- Conditional Access status shows:
  - Policy applied successfully
  - Grant controls satisfied
  - No authentication failures

📸 Evidence: `06-signin-logs-hardened-ca.png`

---

## Observations & Analysis
- Conditional Access evaluates multiple signals:
  - User identity
  - Device compliance
  - Authentication state
- MFA does not trigger unnecessarily when conditions are satisfied
- Hardened policies increase security without degrading usability
- Sign-in logs provide clear visibility into policy evaluation

This mirrors real-world enterprise Conditional Access design.

---

## Security Concepts Demonstrated
- Conditional Access policy design
- MFA enforcement logic
- Device-based access control
- Zero Trust principles
- Authentication session reuse
- Identity risk reduction without user disruption

---

## Key Takeaways
- Conditional Access is evaluated every sign-in, even when not triggered
- MFA should be adaptive, not constant
- Device compliance is a critical identity signal
- Hardened policies must balance security and productivity
- Sign-in logs are essential for troubleshooting and audits

This lab establishes a hardened authentication baseline that will be extended in future labs using risk-based access, Privileged Identity Management (PIM), and Microsoft Graph automation.
