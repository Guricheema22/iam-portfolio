# Lab 06 – Identity Lifecycle Management (Joiner / Mover / Leaver)

## Overview

This lab demonstrates **enterprise-grade Identity Lifecycle Management (ILM)** using Microsoft Entra ID, with a strong focus on the **Mover scenario**, which represents the highest real-world IAM risk.

The objective is to simulate a **department change** for an existing user, ensure **old access is revoked**, **new access is granted**, and **baseline access is retained**, following least-privilege and Zero Trust principles.

This mirrors how identity changes are handled in production enterprise environments.

---

## Scope

This lab focuses on:

- Identity lifecycle operations (Joiner / Mover / Leaver)
- Group-based access control
- Access revocation and reassignment
- Risk analysis of mover scenarios
- Audit and verification of access changes

---

## Scenario

**User:** John Smith  
**Current Department:** General Business  
**New Department:** Finance  

### Existing Group Membership
- `M365-Business-Users` (Baseline Access)

### Target Group Membership
- `M365-Business-Users` (Retained)
- `Finance` (New Role-Based Access)

---

## Key IAM Principle Applied

> **Baseline access remains. Role-based access changes.**

This prevents:
- Privilege creep
- Accidental over-permission
- Operational disruption

---

## Step-by-Step Implementation

---

### 1. Identify Existing User and Groups

- Navigated to **Microsoft Entra ID → Users**
- Located user **John Smith**
- Reviewed current group memberships

**Confirmed:**
- User is a member of `M365-Business-Users`
- No Finance access assigned yet

📸 **Evidence:**  
`evidence/01-user-existing-groups.png`

---

### 2. Validate Baseline Access Group (Must Remain)

- Reviewed purpose of `M365-Business-Users`
- Confirmed it provides:
  - Microsoft 365 access
  - Email, Teams, SharePoint
  - Core business services

**Decision:**
- Baseline group **must NOT be removed**

📸 **Evidence:**  
`evidence/02-baseline-group-retained.png`

---

### 3. Simulate Mover Event (Department Change)

- Business requirement received:  
  **John Smith moves from Business to Finance**
- Identified Finance-specific access requirements

📸 **Evidence:**  
`evidence/03-mover-scenario-defined.png`

---

### 4. Grant New Role-Based Access (Finance)

- Added user to **Finance** security group
- This group represents:
  - Financial systems
  - Sensitive data access
  - Role-specific permissions

📸 **Evidence:**  
`evidence/04-finance-group-added.png`

---

### 5. Revoke Old Role-Based Access (If Applicable)

- Reviewed for any legacy role groups (e.g. Reception, Sales)
- Confirmed no conflicting role-based access remains

**Result:**
- No unnecessary permissions retained
- No access overlap

📸 **Evidence:**  
`evidence/05-old-access-reviewed.png`

---

### 6. Post-Move Access Validation

- Verified final group membership:
  - `M365-Business-Users` ✅
  - `Finance` ✅
- Confirmed access aligns with new job function

📸 **Evidence:**  
`evidence/06-final-group-membership.png`

---

### 7. Risk Analysis – Why Mover Is Highest Risk

Mover scenarios are the **most dangerous phase** in identity lifecycle because:

- Access is **added**, not reset
- Old permissions are often forgotten
- Privilege accumulation occurs silently
- Financial and sensitive systems are commonly involved

Failure at this stage leads to:
- Excessive permissions
- Audit findings
- Security incidents

This lab explicitly mitigates that risk.

---

## Security & IAM Concepts Demonstrated

- Identity lifecycle governance
- Least privilege enforcement
- Role-based access control (RBAC)
- Privilege deconfliction
- Access revocation discipline
- Audit readiness

---

## Enterprise Relevance

This lab reflects how organisations:

- Manage internal role changes
- Prevent access creep
- Support audits and compliance
- Reduce insider risk
- Enforce Zero Trust identity principles

---

## Key Takeaways

- Baseline access should **never be removed** during a role change
- Role-based access **must be explicitly revoked and reassigned**
- Mover scenarios require the **most scrutiny**
- Group-based access enables scalable IAM operations
- Proper lifecycle management prevents long-term security debt

---

## Next Improvements (Future Labs)

- Automate mover handling using Dynamic Groups
- Integrate approval workflows
- Trigger access reviews post-move
- Extend to hybrid identity scenarios

---

