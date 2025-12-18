## Project 03 – Break-Glass Emergency Access Accounts

### Scenario
The organisation requires a safe recovery mechanism in case administrators
are locked out due to MFA outages, Conditional Access misconfiguration,
or identity service issues.

### What I implemented
- Created a dedicated cloud-only emergency access account
- Assigned Global Administrator role for full tenant recovery
- Designed the account to bypass normal authentication controls
- Ensured the account is not used for day-to-day administration

### Design Decisions
**Decision 1: Create a dedicated break-glass account**
- Separates emergency access from daily admin accounts
- Reduces risk of permanent tenant lockout

**Decision 2: Assign Global Administrator role**
- Ensures full recovery capability during identity incidents
- Avoids partial access during critical outages

**Decision 3: Exclude break-glass account from MFA and Conditional Access**
- Prevents lockout if MFA or Conditional Access services fail
- Aligns with Microsoft-recommended emergency access design

### Risks Mitigated
- Complete administrative lockout
- Inability to recover from identity misconfiguration
- Prolonged security incidents due to lack of access

### Security Controls
- Strong, long password stored securely
- Account usage restricted to emergency scenarios only
- Intended monitoring and alerting for any sign-in activity

### Evidence
- Break-glass account created (cloud-only)
- Global Administrator role assignment verified

### Scope Note
This project was performed in an active Entra ID tenant.
The break-glass account was created for learning and design purposes
and is not used for daily administrative activities.

### What I would improve next
- Configure alerting on break-glass account sign-ins
- Create a second break-glass account for redundancy
- Periodically test emergency access under controlled conditions
