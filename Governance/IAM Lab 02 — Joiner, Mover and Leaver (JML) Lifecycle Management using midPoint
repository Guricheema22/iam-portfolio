# IAM Lab 02 — Joiner, Mover and Leaver (JML) Lifecycle Management using midPoint

# Lab Overview

This lab focused on implementing enterprise-style Joiner, Mover, and Leaver (JML) lifecycle management using midPoint integrated with an HR authoritative source.

The objective of this lab was to understand how IAM platforms automate:

- onboarding new employees
- synchronizing identity updates
- processing employee terminations
- automating lifecycle governance workflows

The HR system was simulated using a CSV file, similar to how enterprise organizations integrate IAM platforms with:

- Workday
- SAP SuccessFactors
- Oracle HCM

midPoint was used as the Identity Governance and Administration (IGA) platform responsible for:

- synchronization
- provisioning
- reconciliation
- lifecycle automation
- governance processing

---

# Technologies Used

- midPoint
- Docker
- PostgreSQL
- CSV Connector
- Synchronization Policies
- Reconciliation Tasks

---

# Enterprise IAM Architecture Simulated

HR CSV File  
→ midPoint Synchronization Engine  
→ Identity Lifecycle Governance  
→ Automated Provisioning / Deprovisioning

---

# Lab Objectives

This lab simulated:

| Lifecycle Event | Description |
|---|---|
| Joiner | New employee onboarding |
| Mover | Employee department transfer |
| Leaver | Employee removal / deprovisioning |

---

# Why Synchronization Policies Were Required

Before lifecycle automation could function correctly, synchronization reactions had to be configured inside midPoint.

IAM platforms must understand:
- how to process new users
- how to update existing users
- how to handle deleted HR identities

Without synchronization rules:
- users may not update correctly
- deleted identities may remain active
- governance workflows cannot automate lifecycle actions

---

# Synchronization Reactions Configuration

![Synchronization_Reactions_Configuration](screenshots/Synchronization_Reactions_Configuration.png)

### Synchronization reactions configured

| Situation | Action |
|---|---|
| Unmatched | Add focus |
| Linked | Synchronize |
| Deleted | Delete focus |

---

# Purpose of Each Synchronization Reaction

## Create User (Unmatched → Add focus)

Automatically creates new identities when new HR users are discovered.

This simulates automated onboarding workflows used in enterprise IAM systems.

---

## Update Existing User (Linked → Synchronize)

Automatically updates identity attributes when HR changes occur.

This simulates Mover lifecycle processing such as:
- department transfers
- organizational changes
- business unit changes

---

## Deleted HR User (Deleted → Delete focus)

Automatically removes identities when users are deleted from the HR source.

This simulates automated Leaver governance and deprovisioning.

---

# Why Reconciliation Task Was Required

Initially, Import Tasks successfully handled:
- onboarding new users
- synchronizing attribute changes

However, deleted users were not automatically removed.

This happened because Import Tasks mainly process:
- active existing accounts currently visible on the HR resource

To detect deleted accounts and synchronization drift, a Reconciliation Task was required.

---

# Difference Between Import Task and Reconciliation Task

| Task Type | Purpose |
|---|---|
| Import Task | Imports current accounts and attribute changes |
| Reconciliation Task | Detects deleted accounts and synchronization inconsistencies |

---

# Enterprise IAM Relevance

This reflects real enterprise IAM architecture where:
- import tasks process onboarding and updates
- reconciliation tasks process deletions and governance drift

This is a core concept in enterprise identity governance.

---

# Reconciliation Task Creation

![Reconciliation_Task_Creation](screenshots/Reconciliation_Task_Creation.png)

A Reconciliation Task was created to continuously compare:
- HR source accounts
- existing IAM identities

This allowed midPoint to detect users removed from the HR system.

---

# Automated Reconciliation Task Configuration

![Reconciliation_Task_Automation](screenshots/Reconciliation_Task_Automation.png)

The Reconciliation Task was configured to execute automatically on a recurring schedule.

This enabled automated governance processing without manual intervention.

---

# Automated Import Task Configuration

![Import_Task_Automation](screenshots/Import_Task_Automation.png)

The Import Task was also automated to process:
- new HR users
- identity updates
- synchronization changes

The task was configured with:
- recurring execution
- 60-second interval

This simulated continuous HR-driven synchronization.

---

# Automated Task Execution

![Automated_Task_Execution_Status](screenshots/Automated_Task_Execution_Status.png)

This screenshot shows automated governance tasks executing successfully.

The environment continuously processed:
- onboarding
- updates
- reconciliation
- lifecycle events

without manually running synchronization tasks.

---

# Mover Lifecycle Demonstration

## Existing Department in midPoint

![Daniel_Wilson_Department_Finance_MidPoint](screenshots/Daniel_Wilson_Department_Finance_MidPoint.png)

Daniel Wilson initially existed in midPoint with department value:
- Finance

---

## Department Changed in HR CSV

![Daniel_Wilson_Department_Change_CSV](screenshots/Daniel_Wilson_Department_Change_CSV.png)

The HR authoritative source was updated to change Daniel Wilson’s department from:
- Finance
→ Sales

This simulated an enterprise Mover lifecycle event.

---

## Department Automatically Updated in midPoint

![Daniel_Wilson_Department_Updated_To_Sales](screenshots/Daniel_Wilson_Department_Updated_To_Sales.png)

After synchronization:
- midPoint automatically updated the linked identity attribute

This validated:
- attribute synchronization
- linked identity updates
- Mover lifecycle automation

---

# Leaver Lifecycle Demonstration

## Aman Kaur Active Identity

![Aman_Kaur_Active_User_MidPoint](screenshots/Aman_Kaur_Active_User_MidPoint.png)

Aman Kaur initially existed as an active identity inside midPoint.

---

## Aman Kaur Removed from HR Source

![Aman_Kaur_Removed_From_HR_CSV](screenshots/Aman_Kaur_Removed_From_HR_CSV.png)

The employee record was removed from the HR CSV file.

This simulated:
- employee termination
- HR-driven Leaver event

---

## Automated Deprovisioning

![Aman_Kaur_Automatically_Deprovisioned](screenshots/Aman_Kaur_Automatically_Deprovisioned.png)

The Reconciliation Task detected that:
- the HR account no longer existed

midPoint then automatically:
- triggered the Deleted synchronization reaction
- removed the identity object from midPoint

This validated:
- automated deprovisioning
- Leaver governance
- reconciliation processing

---

# IAM Concepts Demonstrated

- Authoritative Source Integration
- Identity Lifecycle Management
- Joiner / Mover / Leaver (JML)
- Synchronization Policies
- Automated Provisioning
- Automated Deprovisioning
- Reconciliation Processing
- Governance Automation
- Lifecycle Synchronization

---

# Enterprise Learning Outcome

This lab strengthened my understanding of how enterprise IAM systems automate lifecycle governance workflows using:
- synchronization tasks
- reconciliation processing
- authoritative source integration
- automated provisioning and deprovisioning

The lab also demonstrated the operational difference between:
- importing active accounts
- reconciling deleted accounts

which is a critical concept in real-world Identity Governance and Administration (IGA) environments.
