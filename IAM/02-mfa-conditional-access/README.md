## Project 02 – MFA & Conditional Access (Entra ID)

### Scenario
The organisation requires stronger protection against credential-based attacks
such as phishing and password reuse. Identity security must be improved while
maintaining operational simplicity for a small environment.

### What I implemented
- Verified Microsoft Entra ID Security Defaults for baseline MFA protection
- Analysed MFA enforcement vs user registration behaviour
- Reviewed authentication methods at the user level
- Designed Conditional Access policies for future enterprise-scale control

### Design Decisions
**Decision 1: Use Security Defaults for baseline MFA**
- Provides immediate MFA enforcement without custom policy complexity
- Aligns with Microsoft-recommended baseline security for small tenants

**Decision 2: Do not pre-register MFA methods for users**
- Users are forced to securely self-register MFA at first sign-in
- Reduces admin handling of authentication secrets

**Decision 3: Design Conditional Access policies without immediate enforcement**
- Allows future granular control when organisational maturity or licensing increases
- Prevents misconfiguration risk in a live tenant

### Risks Mitigated
- Credential theft and phishing attacks
- Password-only authentication
- Privileged account compromise

### Conditional Access Policy Design (Planned)
- Require MFA for all users accessing cloud applications
- Enforce stricter MFA requirements for administrative roles
- Block high-risk sign-in attempts based on identity risk

### Evidence
- Security Defaults enabled (tenant-level)
- User authentication methods showing MFA registration required
- Conditional Access policies reviewed (no custom policies applied)

### Scope Note
This project was performed in an active Entra ID tenant.
No changes were made that could impact production users.
All observations were conducted using test identities only.

### What I would improve next
- Implement Conditional Access policies in report-only mode
- Introduce break-glass accounts excluded from MFA policies
- Add sign-in log monitoring for identity-based incidents
