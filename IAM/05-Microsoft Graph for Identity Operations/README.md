# Lab 05 – Microsoft Graph for Identity Operations

## Overview
This lab demonstrates how Microsoft Graph is used for enterprise-scale Identity and Access Management (IAM) operations.  
The focus is on non-human identities, permissions, governance-style queries, and lifecycle validation beyond portal-based checks.

This lab reflects real-world IAM consulting and enterprise security operations.

---

## High-Level Flow

1. App Registration (Graph access)
2. Permissions & Admin Consent
3. Microsoft Graph Explorer authentication
4. Baseline identity queries
5. Account status validation
6. Governance-style (aged access) reporting
7. Enterprise IAM relevance and takeaways

---

## Step-by-Step Implementation

---

### 1. Create App Registration (Non-Human Identity)

- Created a new App Registration in Microsoft Entra ID
- Represents a non-human identity used for automation and reporting
- Common enterprise pattern for service-to-service access

Evidence:
- evidence/01-app-registration-created.png

---

### 2. Assign Microsoft Graph API Permissions

- Assigned Microsoft Graph application permissions to the app
- Permissions granted:
  - User.Read.All
  - Directory.Read.All
- Enables tenant-wide identity visibility

Evidence:
- evidence/02-api-permissions-assigned.png

---

### 3. Grant Admin Consent

- Granted admin consent for the tenant
- Ensures permissions are approved centrally
- Demonstrates permission governance and least-privilege awareness

Evidence:
- evidence/03-admin-consent-granted.png

---

### 4. Sign in to Microsoft Graph Explorer

- Signed in to Microsoft Graph Explorer
- Confirmed authentication context
- Verified readiness to execute Graph queries

Evidence:
- evidence/04-graph-explorer-signed-in.png

---

### 5. Run Baseline User Query (200 OK Validation)

- Executed a baseline Microsoft Graph query to retrieve user objects
- Selected key identity attributes commonly used in IAM operations:
  - displayName
  - userPrincipalName
  - accountEnabled

Query Executed:
GET https://graph.microsoft.com/v1.0/users?$select=displayName,userPrincipalName,accountEnabled

Results:
- Request returned HTTP 200 OK
- User objects successfully retrieved

Evidence:
- evidence/05-users-query-200-ok.png

---

### 6. Account Status Validation

- Reviewed the accountEnabled attribute in the Graph response
- Confirmed active users returned:
  - accountEnabled: true
- Enables programmatic verification of account lifecycle state

Supports:
- Deprovisioning checks
- Dormant account detection
- Automated lifecycle workflows

Evidence:
- evidence/06-account-enabled-true.png

---

### 7. Governance-Style Query (Aged Access Example)

- Executed a governance-style query to identify identities requiring review
- Example enterprise use case:
  - Users or guest accounts older than a defined threshold (e.g. 90 days)

Mirrors real-world IAM governance activities:
- Access reviews
- External user clean-up
- Audit and compliance reporting

These queries are typically:
- Scheduled
- Automated
- Exported to security or compliance teams

Evidence:
- evidence/07-governance-query-aged-access.png

---

## Security & IAM Concepts Demonstrated

- Non-human identities (application registrations)
- Least-privilege permission assignment
- Admin consent governance
- Programmatic identity visibility
- Lifecycle state validation
- Identity governance and audit readiness
- Automation-first IAM design

---

## Enterprise Relevance

This lab reflects how organisations:
- Automate access reviews
- Detect stale or risky identities
- Support audit and compliance requirements
- Integrate identity data into security tooling

---

## Key Takeaways

- Microsoft Graph enables identity operations beyond portal limitations
- Enterprise IAM relies on automation, not manual checks
- Programmatic access is essential for governance and compliance
- Graph-based reporting scales to thousands of identities
- This approach mirrors real-world IAM consulting and enterprise operations
