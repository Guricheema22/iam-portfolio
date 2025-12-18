# Project 04 – Privileged Access Management (PIM) – Design & Validation

## Scenario
The organisation requires strict control over privileged administrative roles to reduce the risk of credential compromise, privilege abuse, and lateral movement attacks.

Standing administrative access presents a high security risk and does not align with Zero Trust or least privilege principles.

---

## Objective
To validate the presence of Microsoft Entra Privileged Identity Management (PIM) and design a secure, enterprise-ready privileged access model using just-in-time (JIT) role activation.

---

## Current Tenant State (Observed)
- Microsoft Entra ID PIM is enabled and accessible
- Global Administrator role is assigned directly (permanent)
- No eligible or active PIM-managed role assignments exist
- PIM role management actions are restricted due to licensing/onboarding state

This reflects a common real-world scenario where PIM is available but not yet enforced tenant-wide.

---

## Design Decision
PIM was **not enforced on Global Administrator** in this tenant to avoid:
- Risk of tenant lockout
- Disruption of administrative access
- Uncontrolled changes in a live directory

Instead, a design-led approach was followed to document best practice.

---

## Recommended Privileged Access Model

### Global Administrator
- Assignment type: Permanent (Break-glass only)
- MFA: Enabled
- Usage: Emergency recovery only
- Reason: Ensures tenant recoverability

### Standard Administrative Roles (e.g. User Administrator)
- Assignment type: Eligible via PIM
- Activation requirements:
  - MFA
  - Justification
  - Time-bound access (1 hour)
- Approval: Optional (based on organisation maturity)

---

## Risk Mitigated
- Privilege escalation attacks
- Admin credential compromise
- Excessive standing access
- Accidental or malicious changes

---

## Alignment with Best Practices
- Microsoft Zero Trust model
- Least privilege access
- Separation of emergency and operational access
- Audit-ready privileged access design

---

## Outcome
This project demonstrates the ability to:
- Assess privileged access posture
- Understand PIM operational constraints
- Design secure, scalable admin access controls
- Make safe decisions in a production-like environment
