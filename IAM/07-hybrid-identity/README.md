# Project 07 – Hybrid Identity Overview (Active Directory & Entra ID)

## Scenario
The organisation operates in a cloud-first model with Microsoft Entra ID as the primary identity provider.
While the current tenant is cloud-only, hybrid identity concepts are required to support environments that integrate on-premises Active Directory with cloud identity services.

---

## Objective
To understand and document hybrid identity architecture, including how on-premises Active Directory integrates with Microsoft Entra ID, and how identity authority and authentication are managed in hybrid environments.

---

## Current Tenant State
- Identity provider: Microsoft Entra ID
- Tenant type: Cloud-only
- On-premises Active Directory: Not present
- Entra ID Connect: Not configured

This reflects a modern cloud-first organisation or a learning tenant without legacy infrastructure.

---

## Hybrid Identity Architecture (Conceptual)

### On-Premises Active Directory
- Manages user and computer accounts within corporate networks
- Acts as the authoritative source for identity attributes in hybrid environments
- Handles on-premises authentication and group-based access

---

### Microsoft Entra ID
- Provides cloud authentication and authorization
- Enforces MFA and Conditional Access
- Controls access to Microsoft 365 and Azure resources

---

### Entra ID Connect
- Synchronisation tool used to connect on-prem AD with Entra ID
- Syncs users, groups, and attributes
- Does not replace on-prem AD

Entra ID Connect only appears in the Entra portal when hybrid sync has been configured.

---

## Authentication Models in Hybrid Identity

### Password Hash Synchronization (Recommended)
- Password hash synced to Entra ID
- Cloud authentication handled by Entra ID
- Minimal on-prem dependency
- Most common and recommended model

---

### Pass-Through Authentication
- Password validation occurs on-premises
- Requires on-prem availability
- Higher operational complexity

---

### Federation (ADFS)
- Legacy authentication model
- Complex to maintain
- Typically used in older enterprise environments

---

## Source of Authority
- On-prem AD is the authoritative source in hybrid identity
- Certain attributes become read-only in Entra ID
- Changes such as password resets or account disablement are performed on-prem

---

## Common Hybrid Identity Issues

**User cannot edit attributes in Entra ID**
- User is synchronized from on-prem AD

**Password reset does not apply immediately**
- Sync delay between AD and Entra ID

**Account disabled in AD but still active in cloud**
- Sync cycle not completed or soft-deleted state

---

## Design Considerations
- Hybrid identity enables gradual cloud adoption
- MFA and Conditional Access are enforced in Entra ID
- On-prem dependency should be minimized where possible
- Cloud-only identities simplify management when legacy systems are retired

---

## Outcome
This project demonstrates the ability to:
- Understand hybrid identity architecture
- Explain Entra ID Connect and authentication models
- Identify source-of-authority behavior
- Troubleshoot common hybrid identity scenarios
- Operate confidently in both cloud-only and hybrid environments
