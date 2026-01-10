# Lab 05 – Microsoft Graph for Identity Operations (Governance & Reporting)

## Overview
This lab demonstrates how **Microsoft Graph** is used for **identity operations, governance, and reporting** in a Microsoft Entra ID environment.

Rather than relying on manual portal checks, this lab focuses on **programmatic identity visibility**, which is essential for enterprise IAM teams responsible for access reviews, lifecycle management, and automation.

---

## Scenario
As the organisation grows, identity administrators must regularly review accounts to ensure access remains appropriate.

Manual reviews in the Entra ID portal do not scale and are not suitable for audit or governance requirements.

The identity administrator must:
- Query directory users programmatically
- Identify accounts requiring governance review
- Produce repeatable, auditable results

---

## Technologies Used
- Microsoft Entra ID
- Microsoft Graph API (v1.0)
- Microsoft Graph Explorer
- Microsoft 365 Tenant

---

## Permissions & Consent Model
This lab uses **delegated permissions** via Microsoft Graph Explorer.

Required permission:
- `User.Read.All` (Delegated)

Permissions were consented using an administrative account to allow **read-only directory access**, following least-privilege principles.

---

## Step-by-Step Implementation

### 1️⃣ Microsoft Graph Explorer Access
- Navigated to **Microsoft Graph Explorer**
- Signed in with an Entra ID administrative account
- Confirmed active access token

📸 Evidence: `01-graph-explorer-signed-in.png`

---

### 2️⃣ Baseline User Query
Executed the following request to retrieve directory users:

```http
GET https://graph.microsoft.com/v1.0/users?$select=displayName,userPrincipalName,accountEnabled
