```markdown
# IAM Lab 01 — HR Authoritative Source Integration using midPoint

# Lab Overview
9
This lab was created to understand how enterprise Identity and Access Management (IAM) systems automate identity onboarding and provisioning using an authoritative HR source.

The goal of this lab was not only to create users inside midPoint, but to understand:
- how IAM workflows operate
- how synchronization works
- why governance configurations are required
- how onboarding automation works in enterprise environments

This lab simulates a simplified enterprise IAM architecture.

---

# Enterprise IAM Architecture Simulated

| Enterprise Function | Lab Technology |
|---|---|
| HR System | CSV File |
| Enterprise HR Equivalent | Workday / SAP SuccessFactors |
| Identity Governance Platform | midPoint |
| Enterprise IGA Equivalent | SailPoint / Saviynt |
| Identity Provider (Future Labs) | Okta |
| Enterprise IdP Equivalent | Okta / Entra ID / Ping Identity |

The CSV file acts as the HR system containing employee records.

midPoint acts as the Identity Governance and Administration (IGA) platform responsible for:
- identity synchronization
- onboarding
- lifecycle management
- governance workflows

Okta will later be integrated as the cloud Identity Provider.

---

# Why Initial midPoint Configuration Was Required

Since this was the first-time setup of the midPoint environment, several configurations had to be created manually before identity onboarding could work properly.

In enterprise IAM systems, platforms do not automatically know:
- what type of accounts are being imported
- how user attributes should map
- what actions to take for new users
- how provisioning workflows should operate

Because of this, initial IAM configuration is required to establish the identity workflow.

This setup is normally performed by IAM engineers during:
- new IAM deployments
- onboarding new HR systems
- connector integrations
- governance platform implementation

---

# Technologies Used

- midPoint
- Docker
- PostgreSQL
- CSV Connector
- PowerShell

---

# IAM Workflow Implemented

HR CSV File
→ Resource Objects
→ Synchronization Engine
→ Shadows
→ User Creation (Add Focus)
→ midPoint Users

---

# Screenshot Evidence and Configuration Explanation

---

## 1. HR_Resource_Objects_Discovered

![HR_Resource_Objects_Discovered](screenshots/HR_Resource_Objects_Discovered.png)

This screenshot shows employee records successfully discovered from the HR CSV file under Resource Objects.

### Why this step is important

Before creating users, midPoint must first detect and read external accounts from the authoritative source.

### What this proves

- CSV connector is working
- HR source is reachable
- identity records are being discovered successfully

### Important IAM Concept

Resource Objects are external identities discovered from connected systems.

---

## 2. Import_Task_Creation_Configuration

![Import_Task_Creation_Configuration](screenshots/Import_Task_Creation_Configuration.png)

This screenshot shows the creation of the Import Task.

### Why this configuration is required

midPoint does not automatically process discovered accounts into users.

The Import Task is responsible for:
- reading external accounts
- applying synchronization rules
- processing identity onboarding workflows

### Enterprise relevance

Real IAM systems regularly run import and reconciliation tasks to synchronize identities from HR systems.

---

## 3. Import_Task_Execution_Successful

![Import_Task_Execution_Successful](screenshots/Import_Task_Execution_Successful.png)

This screenshot shows the Import Task running successfully.

### What this validates

- connector communication
- task execution
- synchronization processing

At this stage:
midPoint could successfully read accounts from the HR source.

However, users were not yet created because additional synchronization settings were still missing.

---

## 4. Object_Type_Configuration_HR_Accounts

![Object_Type_Configuration_HR_Accounts](screenshots/Object_Type_Configuration_HR_Accounts.png)

This screenshot shows Object Type configuration.

### Configured values

- Kind = Account
- Intent = default
- Focus Type = User

### Why this configuration is required

midPoint needs to understand what type of objects are being imported.

This configuration tells midPoint:

"These HR records represent user accounts that should become User identities."

Without this setup:
- synchronization cannot function correctly
- provisioning actions cannot execute properly

### Enterprise relevance

IAM engineers configure object types whenever integrating:
- HR systems
- Active Directory
- cloud applications
- identity sources

---

## 5. Import_Task_Skipped_Accounts_No_Sync_Policy

![Import_Task_Skipped_Accounts_No_Sync_Policy](screenshots/Import_Task_Skipped_Accounts_No_Sync_Policy.png)

This screenshot shows the Import Task skipping all accounts.

### Observed issue

- accounts were discovered successfully
- but users were not created

### Root cause

No synchronization policy or inbound mappings were configured yet.

### Why this happened

midPoint could see external accounts but did not know:
- what attributes to map
- what action to take for new identities
- how onboarding should occur

### Important IAM concept

Discovery does not automatically mean provisioning.

IAM systems require synchronization policies to define:
- onboarding actions
- identity correlation
- provisioning workflows

This was an important troubleshooting exercise demonstrating real IAM workflow behavior.

---

## 6. Inbound_Mappings_Configuration

![Inbound_Mappings_Configuration](screenshots/Inbound_Mappings_Configuration.png)

This screenshot shows inbound attribute mappings configured.

### Mappings created

| Resource Attribute | midPoint Attribute |
|---|---|
| email | name |
| email | emailAddress |
| fullName | fullName |
| department | locality |

### Why inbound mappings are required

Inbound mappings define how identity data flows from the HR source into IAM identities.

### Examples

- HR email becomes IAM username
- employee full name becomes display name

### Why email was mapped to name

The `name` attribute in midPoint is the unique identity identifier required for user creation.

### Enterprise relevance

Attribute mapping is a critical part of IAM engineering because every system stores identity data differently.

---

## 7. Synchronization_Reaction_Add_Focus

![Synchronization_Reaction_Add_Focus](screenshots/Synchronization_Reaction_Add_Focus.png)

This screenshot shows synchronization reaction configuration.

### Configured values

- Situation = Unmatched
- Action = Add Focus

### Why this configuration is required

This rule tells midPoint:

"If an HR account exists but no matching user exists, automatically create a new user."

This is the actual onboarding automation workflow.

Without this configuration:
- accounts would only be discovered
- users would not be provisioned

### Enterprise relevance

This is similar to Joiner automation workflows used in:
- SailPoint
- Saviynt
- Okta Lifecycle
- Microsoft Entra provisioning

---

## 8. Import_Task_Rerun_Successful_Provisioning

![Import_Task_Rerun_Successful_Provisioning](screenshots/Import_Task_Rerun_Successful_Provisioning.png)

This screenshot shows the Import Task executed again after synchronization settings were configured.

### Results

- users were processed successfully
- onboarding workflow completed
- provisioning succeeded

### Important learning

Once synchronization policies and mappings were configured correctly, automated identity creation worked successfully.

---

## 9. MidPoint_Users_Created_Successfully

![MidPoint_Users_Created_Successfully](screenshots/MidPoint_Users_Created_Successfully.png)

This screenshot shows users successfully created inside midPoint.

### This confirms

- HR integration worked
- synchronization policies worked
- inbound mappings worked
- automated provisioning succeeded

### Final outcome

Employee records from the HR source were successfully converted into managed IAM identities.

---

# Key IAM Concepts Learned

## Authoritative Source

The HR system acts as the trusted source of identity information.

---

## Resource Objects

External accounts discovered from connected systems.

---

## Shadows

Internal references of external resource accounts stored by midPoint.

---

## Focus Objects

Managed identities created inside the IAM platform.

---

## Synchronization Policies

Rules defining how IAM reacts to identity events.

---

## Inbound Mappings

Rules controlling how identity attributes move between systems.

---

## Automated Provisioning

Automatic creation of identities based on synchronization logic.

---

# Important Troubleshooting Scenario

One important IAM troubleshooting scenario occurred during this lab.

### Problem

Import Task detected accounts but skipped user creation.

### Root cause

No synchronization policy configured.

### Resolution

Configured:

Unmatched → Add Focus

### Result

midPoint successfully created users automatically.

This troubleshooting exercise helped reinforce the difference between:
- account discovery
- synchronization
- actual identity provisioning
