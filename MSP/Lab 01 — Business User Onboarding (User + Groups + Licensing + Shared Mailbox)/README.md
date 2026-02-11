# Lab 01 — Business User Onboarding (User + Groups + Licensing + Shared Mailbox)

## 🔹 Scenario
A new employee, **Michael Scott**, has joined the Finance department.  
This lab demonstrates the full onboarding workflow in a Microsoft 365 environment:

- Create a new user  
- Assign department security groups  
- Assign Microsoft 365 licensing  
- Create a shared mailbox for Finance  
- Grant delegated mailbox permissions  
- Verify final configuration  

---

## 🔹 Environment
- Microsoft 365 Dev Tenant  
- Admin Centers Used:
  - Microsoft Entra ID
  - Microsoft 365 Admin Center
  - Exchange Admin Center  
- Role: Global Administrator / User Administrator  

---

## 🔹 Tasks Performed

---

### **1. Created a New User (Michael Scott)**
- Navigated to **Entra ID → Users → New User**
- Created *Michael Scott* with auto-generated password
- Enabled password change at first sign-in

📸 `images/01-new-user-michael-scott.png`

---

### **2. Assigned Security Groups**
Added Michael to:

- **Finance-Users**
- **M365-Business-Users**

These groups control departmental access and permissions.
  
📸 `images/02-added-to-finance-group.png`

---

### **3. Assigned Microsoft 365 License**
Assigned license:

- **Microsoft 365 Business Premium**

📸 `images/03-license-assignment-michael.png`

---

### **4. Created the Finance Shared Mailbox**
Created a shared departmental mailbox:

- **Finance Shared Mailbox**  
- Email: `finance@tenant.onmicrosoft.com`

📸 `images/04-create-finance-shared-mailbox.png`

---

### **5. Granted Shared Mailbox Permissions**
Assigned:

- **Full Access**
- **Send As**

to Michael Scott.

📸 `images/05-finance-mailbox-delegation.png`  

---

### **6. Verified Permissions & Group Membership**
Verification completed:

- Confirmed correct group membership  
- Confirmed mailbox type = *SharedMailbox*  
- Confirmed delegation permissions  

📸 `images/06-michael-groups-confirmation.png`  

---

## 🔹 Understanding Shared Mailboxes
A shared mailbox is a team mailbox rather than an individual one.  
It allows multiple employees to:

- Read incoming emails  
- Reply as the department (using Send As)  
- Share conversation history  
- Maintain continuity even when staff change  

Shared mailboxes do **not** require a license if under 50GB and are commonly used for:

- finance@
- hr@
- admin@
- support@

---

## 🔹 Outcome
Completed a full business onboarding workflow:

- New user provisioned  
- Groups and departmental permissions assigned  
- License applied  
- Shared mailbox created  
- Mailbox access delegated  
- Configuration verified  

This reflects real identity and mailbox administration in Microsoft 365.

---

## 🔹 Skills Demonstrated
- Entra ID user lifecycle management  
- Security group administration  
- License assignment  
- Shared mailbox creation  
- Delegation (Full Access + Send As)  
- Identity & mailbox configuration documentation  
