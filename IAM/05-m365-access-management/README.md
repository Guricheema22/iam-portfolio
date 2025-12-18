# Project 05 – Microsoft 365 Access Management (Identity-First)

## Scenario
The organisation uses Microsoft 365 for email and collaboration.  
The tenant is managed via a Cloud Solution Provider (CSP), where Microsoft 365 services are administered through a partner portal rather than the native Microsoft 365 Admin Center.

Identity and access management are handled through Microsoft Entra ID.

---

## Objective
To validate and manage Microsoft 365 user access using an identity-first approach, focusing on:
- User sign-in eligibility
- Authentication enforcement
- Mailbox access validation
- Understanding CSP-managed tenant limitations

---

## Tenant Architecture
- Identity provider: Microsoft Entra ID
- Microsoft 365 licensing and service administration: CSP (GoDaddy)
- Security posture: Microsoft Security Defaults enabled

This reflects a common real-world SMB and partner-managed environment.

---

## Access Validation Performed

### User Identity
- User account exists in Entra ID
- Account status: Enabled (sign-in allowed)
- No privileged directory roles assigned

---

### Authentication & MFA
- MFA enforcement governed by Security Defaults
- No per-user MFA methods pre-configured
- MFA registration occurs at first successful sign-in
- Aligns with Microsoft baseline security recommendations

---

### Mailbox & Email Access
- Mailbox provisioning and access validated via CSP portal
- User able to sign in to Outlook Web
- Email access tied to license presence managed by CSP

---

## Design Decisions

### Identity-First Management
- Access validation performed at identity level rather than service configuration
- Authentication controlled centrally through Entra ID policies
- Reduced reliance on per-user configuration

---

### CSP-Aware Administration
- Microsoft 365 Admin Center and Exchange Admin Center are abstracted by CSP
- Identity troubleshooting remains fully accessible via Entra ID
- Clear separation of identity vs service administration responsibilities

---

## Common Access Issues & Resolution Approach

**Issue:** User cannot access email  
**Checks performed:**
1. Verify user exists in Entra ID
2. Confirm account status is enabled
3. Validate MFA enforcement via Security Defaults
4. Confirm mailbox access through CSP portal

---

## Risk Mitigated
- Unauthorized access due to weak authentication
- Misconfiguration from per-user MFA handling
- Over-privileged administrative access
- Confusion between identity and service ownership

---

## Alignment with Best Practices
- Zero Trust identity model
- Least privilege access
- Tenant-wide security enforcement
- CSP-aware operational support

---

## Outcome
This project demonstrates the ability to:
- Manage Microsoft 365 access in a partner-managed tenant
- Troubleshoot user access issues using identity-first principles
- Operate effectively within real-world administrative constraints
- Communicate clearly between identity and service management boundaries
