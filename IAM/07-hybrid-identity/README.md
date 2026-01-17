# Lab 07 — Hybrid Identity Migration (Active Directory → Microsoft Entra ID)

This lab demonstrates a full hybrid identity deployment using:
- On-premises Active Directory Domain Services (AD DS)
- Microsoft Entra Connect Sync
- Group & user provisioning from AD to Entra
- Identity lifecycle + cloud provisioning validation

This lab mirrors *real enterprise conditions* where organisations maintain AD as the authoritative identity source while extending identity to the cloud for M365 and SaaS apps.

---

## 🏗️ Architecture Overview

**Components:**
- On-premises Domain Controller  
- Active Directory Users & Groups  
- Azure tenant with custom domain  
- Microsoft Entra Connect Sync (latest version)  
- Hybrid identity source-of-authority: AD DS  

**Flow:**
AD Users/Groups → Entra Connect Sync → Microsoft Entra ID
---

## 📌 Scope

This lab performs an enterprise-style hybrid migration including:

- Creating organisational OUs  
- Creating and structuring on-prem AD users & groups  
- Assigning on-prem roles through security groups  
- Installing Microsoft Entra Connect  
- Validating hybrid identity sync  
- Verifying source-of-authority attributes  
- Mapping on-prem identities to cloud objects  

This simulates the identity model used by **most enterprise organisations today**.

---

## 👥 Users and Groups Created

**Organisational Units:**
- `Esimxpress`
  - `Users`
  - `Groups`

**Security Groups:**
- `Finance`
- `HR`
- `M365-Business-Users`

**Users (6 total):**
- Andrew Parker (a.parker)
- Sarah Smith (s.smith)
- Michael Jones (m.jones)
- Emily Brown (e.brown)
- John Carter (j.carter)
- Olivia Patel (o.patel)

Each user created in **AD only**, no cloud creation.

📸 *Evidence:*  
- `evidence/01-ou-structure.png`  
- `evidence/02-ad-users-created.png`  
- `evidence/03-ad-groups-created.png`

---

## 🪜 Step-by-Step Implementation

---

### 1️⃣ Create Organisational Units

- Open **Active Directory Users and Computers**
- Right-click domain → *New → Organizational Unit*
- Create:
  - `Esimxpress`
  - Inside it create:
    - `Users`
    - `Groups`

📸 Evidence:  
- `evidence/01-ou-created.png`

---

### 2️⃣ Create Security Groups

- Inside `Groups` OU → *New → Group*
- Group type: **Security**
- Group scope: **Global**
- Create:
  - `Finance`
  - `HR`
  - `M365-Business-Users`

📸 Evidence:  
- `evidence/02-groups-created.png`

---

### 3️⃣ Create On-Prem Users

For each user:
- Right-click `Esimxpress → Users → New → User`
- Set UPN suffix: `@lab.local`
- Specify:
  - First/Last name
  - User logon name
  - Password (uncheck "User must change password")

Add users to appropriate groups.

📸 Evidence:  
- `evidence/03-users-created.png`
- `evidence/04-users-in-groups.png`

---

### 4️⃣ Install Microsoft Entra Connect

Steps performed:
- Downloaded Entra Connect from Entra Admin Portal (not Microsoft Download Center)
- Ran installer on Domain Controller
- Selected **Express Setup**
- Signed in with Entra Global Administrator  
- Provided AD DS enterprise admin credentials

📸 Evidence:  
- `evidence/05-entra-connect-install.png`
- `evidence/06-connect-ad-ds.png`

---

### 5️⃣ Microsoft Entra Sign-In Configuration

- Detected AD UPN suffix: `lab.local`
- No matching cloud domain → Clicked **Continue without matching**
- Proceeded with hybrid sync configuration

📸 Evidence:  
- `evidence/07-signin-config.png`

---

### 6️⃣ Initial Synchronisation

- Completed configuration
- Sync started automatically
- Verified sync status in:
  - Entra Admin → **Identity → Synchronization**
  - Sync cycles (green check mark)

📸 Evidence:
- `evidence/08-sync-success.png`

---

### 7️⃣ Validate User Sync in Entra

For each user:
- Go to **Entra Admin → Users**
- Confirm:
  - User exists
  - `On-premises sync enabled: Yes`
  - `On-premises distinguished name` matches AD
  - `Source: Windows Server AD`
  - `On-premises UPN`, `SAM account name`, and SID present

📸 Evidence:
- `evidence/09-user-cloud-properties.png`

---

### 8️⃣ Validate Group Sync and Membership

- Go to **Entra Admin → Groups**
- Ensure groups:
  - `Finance`
  - `HR`
  - `M365-Business-Users`
  have synced
- Validate cloud membership matches AD membership

📸 Evidence:
- `evidence/10-group-cloud-properties.png`

---

## 🔐 Security & IAM Concepts Demonstrated

- Directory source of authority (AD DS → Entra)
- Immutable ID mapping  
- Object matching and provisioning  
- UPN suffix alignment challenges  
- Group-based access provisioning  
- Hybrid identity lifecycle  
- Synchronisation health monitoring  
- Enterprise OU and group design  
- Admin credential separation  
- Understanding hybrid identity risk  
- Cloud readiness for full modernisation  

---

## 🏢 Enterprise Relevance

This lab reflects how real organisations:

- Maintain hybrid identity for years  
- Use AD as authoritative identity source  
- Synchronise users/groups to Entra  
- Modernise authentication workloads  
- Prepare for Conditional Access, MFA, Intune  
- Lay foundation for Zero Trust  

Most Australian enterprises (Gov, Health, Education, Finance) are in exactly this hybrid stage today.

---

## 📌 Key Takeaways

- Hybrid identity is the **most common** architecture in the world  
- AD remains the **system of record** until fully modernised  
- Entra Connect establishes authoritative identity mapping  
- Cloud objects reflect AD attributes, not vice-versa  
- Proper OU & group design is critical for smooth migration  
- This lab simulates REAL enterprise IAM engineering  
- This is a high-value project for recruiters—shows practical hands-on skill  

---



