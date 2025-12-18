# Project 06 – Azure Access Control using RBAC

## Scenario
The organisation uses Microsoft Azure for cloud resources.
Users authenticate using Microsoft Entra ID, but access to Azure resources must be explicitly granted using Azure Role-Based Access Control (RBAC).

---

## Objective
To validate and implement identity-based access to Azure resources using least privilege principles.

---

## Azure Access Model
- Identity provider: Microsoft Entra ID
- Resource scope: Azure Subscription
- Access control: Azure RBAC

Authentication and authorization are handled as separate processes.

---

## Access Validation Performed

### Authentication
- Test user successfully authenticated via Entra ID
- User able to sign into Azure portal

---

### Authorization (RBAC)
- No resource visibility prior to role assignment
- Reader role assigned at subscription scope
- User gained read-only access to Azure resources
- No modification permissions granted

---

## Design Decision

### Role Selection
- Role used: Reader
- Reason:
  - Allows visibility into resources
  - Prevents configuration changes
  - Aligns with least privilege principle

---

### Scope Selection
- Scope: Subscription
- Reason:
  - Simplifies access management
  - Suitable for read-only operational visibility

---

## Risk Mitigated
- Unauthorized resource modification
- Over-privileged access
- Accidental infrastructure changes

---

## Alignment with Best Practices
- Separation of authentication and authorization
- Identity-first access control
- Least privilege access
- Clear RBAC scoping

---

## Outcome
This project demonstrates the ability to:
- Distinguish Entra ID roles from Azure RBAC roles
- Grant Azure access safely using RBAC
- Troubleshoot resource visibility issues
- Apply enterprise access control principles in Azure
