## Project 01 – Entra ID User & Group Management

### Scenario
EsimXpress requires a secure and scalable approach to manage
user identities and access in the cloud using Microsoft Entra ID.

### What I implemented
- Created cloud user identities in Microsoft Entra ID
- Designed security groups for role-based access control
- Managed access using group membership
- Simulated Joiner, Mover, and Leaver identity lifecycle events

### Design Decisions
- Used security groups instead of direct user permissions
- Followed least privilege by assigning no default roles or licenses

### Risks Mitigated
- Privilege creep from direct permissions
- Orphaned access during role changes
- Unauthorized access by former employees

### Evidence
- Entra ID tenant overview (redacted)
- User list showing test cloud identities
- Security group membership for authorization

### Scope Note
This lab was performed in an existing Entra ID tenant.
Pre-existing organisational accounts were left untouched.
All IAM activities were carried out using dedicated test users only.

### What I would improve next
- Enforce MFA using Conditional Access
- Introduce access reviews for sensitive groups
