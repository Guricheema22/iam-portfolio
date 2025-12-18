# Project 08 – Identity Incidents & Troubleshooting

## Overview
This project documents common identity-related incidents and the structured approach used to investigate, resolve, and mitigate risk within Microsoft Entra ID environments.

The focus is on operational readiness rather than configuration-heavy labs.

---

## Incident Handling Framework
All identity incidents were handled using the following method:

Symptoms → Scope → Root Cause → Resolution → Risk Mitigation

This ensures minimal disruption and avoids unnecessary security changes.

---

## Incident 1 – User Cannot Sign In

### Symptoms
User reports inability to sign in to Microsoft services.

### Investigation
- Verified account status in Entra ID
- Reviewed sign-in logs for failure reason
- Identified authentication or policy-related errors

### Resolution
- Addressed the specific failure (password reset, MFA registration guidance, or account re-enable with approval)

### Risk Mitigated
- Prevented unauthorized access
- Avoided unnecessary policy changes

---

## Incident 2 – MFA Registration or Authentication Issues

### Symptoms
User unable to complete MFA or lost registered device.

### Investigation
- Verified user identity
- Reviewed authentication methods
- Confirmed MFA enforcement via tenant policy

### Resolution
- Reset MFA registration
- Guided user through secure re-registration

### Risk Mitigated
- Maintained MFA enforcement
- Prevented MFA bypass

---

## Incident 3 – Ex-Employee Still Has Access

### Symptoms
HR notification that a former employee can still sign in.

### Investigation
- Verified account status
- Reviewed sign-in activity
- Checked group and role assignments

### Resolution
- Disabled the account immediately
- Removed group memberships
- Reviewed privileged roles

### Risk Mitigated
- Eliminated unauthorized access
- Preserved audit trail for investigation

---

## Incident 4 – Privileged Role Misuse

### Symptoms
Unexpected changes detected by an administrative account.

### Investigation
- Reviewed role assignments
- Checked audit and activity logs
- Validated justification and scope

### Resolution
- Contained access
- Escalated to security where appropriate
- Documented findings

### Risk Mitigated
- Reduced blast radius
- Ensured accountability

---

## Key Principles Applied
- Least privilege
- Identity-first troubleshooting
- Minimal change approach
- Audit and evidence preservation

---

## Outcome
This project demonstrates the ability to:
- Troubleshoot real-world identity issues
- Use logs effectively
- Respond calmly to security-sensitive incidents
- Operate in IAM, Cloud Support, and Security roles
