# Lab 05 – Microsoft Graph for Identity Operations (Enterprise IAM)

## Overview

This lab demonstrates how Microsoft Graph is used to perform identity operations that cannot be efficiently achieved through the Microsoft Entra ID portal alone.

The objective is to showcase **automation-first IAM design**, where identity data is queried programmatically to support governance, lifecycle management, and audit readiness — reflecting real-world enterprise IAM and consulting practices.

---

## Scenario

An organisation requires programmatic visibility into identity data to support:

- Lifecycle management
- Governance and compliance
- Detection of stale or risky identities
- Scalable reporting across thousands of users

Manual portal checks do not scale, so Microsoft Graph is used as the authoritative identity API.

---

## Technologies Used

- Microsoft Entra ID
- Microsoft Graph API
- Microsoft Graph Explorer
- Azure App Registrations
- Microsoft Entra ID Governance concepts

---

## High-Level Flow

This lab is completed in controlled phases:

1. App Registration (Non-human identity)
2. Permissions and Admin Consent
3. Microsoft Graph identity queries
4. Governance-style reporting use cases

---

## Step-by-Step Implementation

---

### 1️⃣ Create App Registration (Non-Human Identity)

- Created a new App Registration in Microsoft Entra ID
- This represents a **non-human identity** used for automation and reporting
- Mirrors enterprise practice where services, scripts, or tools access identity data

📸 Evidence:
- `evidence/01-app-registration-created.png`

---

### 2️⃣ Assign Microsoft Graph API Permissions

- Added Microsoft Graph API permissions to the application
- Permissions assigned (Application permissions):
  - `User.Read.All`
  - `Directory.Read.All`
- Permissions scoped to **read-only access** following least-privilege principles

📸 Evidence:
- `evidence/02-api-permissions-assigned.png`

---

### 3️⃣ Grant Admin Consent

- Granted tenant-wide admin consent for assigned permissions
- Confirms governance approval for programmatic access
- Validates permission and consent management process

📸 Evidence:
- `evidence/03-admin-consent-granted.png`

---

### 4️⃣ Sign In to Microsoft Graph Explorer

- Signed in to Microsoft Graph Explorer using tenant credentials
- Confirmed authentication and readiness to execute Graph queries

📸 Evidence:
- `evidence/04-graph-explorer-signed-in.png`

---

### 5️⃣ Run Baseline User Query (200 OK Validation)

- Executed a baseline Microsoft Graph query to retrieve users
- Selected key identity attributes commonly used in IAM operations:
  - `displayName`
  - `userPrincipalName`
  - `accountEnabled`

```http
GET https://graph.microsoft.com/v1.0/users?$select=displayName,userPrincipalName,accountEnabled



6️⃣ Account Status Validation

Reviewed the accountEnabled attribute in the Graph response

Confirmed active users returned:

accountEnabled: true

Enables programmatic verification of account lifecycle state

Supports:

Deprovisioning checks

Dormant account detection

Automated lifecycle workflows

📸 Evidence:

evidence/06-account-enabled-true.png

7️⃣ Governance-Style Query (Aged Access Example)

Executed a governance-style query to identify identities requiring review

Example enterprise use case:

Users or guest accounts older than a defined threshold (e.g. 90 days)

Mirrors real-world IAM governance activities:

Access reviews

External user clean-up

Audit and compliance reporting

These queries are typically:

Scheduled

Automated

Exported to security or compliance teams

📸 Evidence:

evidence/07-governance-query-aged-access.png

Security & IAM Concepts Demonstrated

Non-human identities (application registrations)

Least-privilege permission assignment

Admin consent governance

Programmatic identity visibility

Lifecycle state validation

Identity governance and audit readiness

Automation-first IAM design

Enterprise Relevance

This lab reflects how organisations:

Automate access reviews

Detect stale or risky identities

Support audit and compliance requirements

Integrate identity data into security tooling

Key Takeaways

Microsoft Graph enables identity operations beyond portal limitations

Enterprise IAM relies on automation, not manual checks

Programmatic access is essential for governance and compliance

Graph-based reporting scales to thousands of identities

This approach mirrors real-world IAM consulting and enterprise operations
