# 🔐 Lab 09 – Microsoft Entra Privileged Identity Management (PIM)

## 📝 Overview
Microsoft Entra **Privileged Identity Management (PIM)** is a security feature that protects elevated/admin access in an organisation.  
Instead of giving users permanent admin roles, PIM provides **Just-In-Time (JIT)**, **time-bound**, **approval-based**, and **audited** access.

This lab demonstrates how PIM is used to:
- Assign an eligible privileged role  
- Require MFA, justification, ticket number, and approval  
- Activate the role as a normal user  
- Approve the request as an administrator  
- Review audit logs for full visibility  

---

# 🧠 Why PIM Is Used (Simple Explanation)
PIM is used because **admin access is dangerous**.  
If a hacker or even an internal user misuses admin rights, they can damage the entire environment.

PIM protects organisations by:
- Removing permanent admin rights  
- Giving admin roles only when needed  
- Enforcing MFA  
- Requiring justification  
- Requiring approval  
- Automatically expiring access  
- Providing full audit logs  

### ✔ Used for:  
- Global Admin  
- User Admin  
- Exchange, SharePoint, Teams Admin  
- Security & Compliance roles  
- Azure resource roles (Owner, Contributor, etc.)

### ❌ Not used for:  
- Normal user permissions  
- File/folder access  
- Group membership  
- Licensing

PIM only protects **privileged** roles.

---

# 🎯 Scenario
Your organisation follows Zero Trust and does **not** allow permanent admin access.  
A support engineer (Emma Brown) needs **User Administrator** rights for a short task.

You will:
1. Assign Emma Brown as **Eligible** for the User Administrator role  
2. Configure PIM with strict controls (MFA, justification, ticket, approval)  
3. Emma activates the role using JIT  
4. Administrator approves the request  
5. Emma receives the role for 1 hour  
6. You view audit logs proving every action  

---

# 🛠️ Configuration Performed in This Lab

### ✔ Assigned eligible privileged role  
Emma Brown was assigned as **Eligible User Administrator**.

### ✔ Configured PIM activation controls  
- Require MFA  
- Require justification  
- Require ticket number  
- Require approval  
- Set maximum duration: **1 hour**  
- Added approver: Global Administrator  

### ✔ Activated role (as test user)  
Emma initiated the activation request and provided justification + ticket number.

### ✔ Approved role request (as administrator)  
Global Admin reviewed and approved the activation request.

### ✔ Verified active assignment  
Emma’s role status became **Active** for 1 hour.

### ✔ Reviewed PIM audit logs  
Observed full lifecycle events including assignment, activation, approval, and expiration.

---

# 🧩 Step-by-Step Summary

## **Step 1 — Assign Eligible Role**
1. Go to: *Microsoft Entra Admin Center → PIM → Microsoft Entra roles → Assignments*
2. Add assignment → Select **User Administrator**
3. Select member: *Emma Brown*
4. Assignment type: **Eligible**
5. Save

📸 *Screenshot 1 — Eligible assignment created*

---

## **Step 2 — Configure Activation Settings**
1. PIM → Settings → Roles  
2. Select **User Administrator**
3. Edit Activation settings:
   - Require MFA → **Yes**
   - Require justification → **Yes**
   - Require ticket → **Yes**
   - Require approval → **Yes**
   - Approver: Global Admin
   - Activation duration: **1 hour**

📸 *Screenshot 2 — Activation Settings (MFA, justification, approval)*

---

## **Step 3 — Activate Role (as Emma Brown)**
1. Log in as test user (incognito)
2. PIM → My roles → Eligible
3. Select **User Administrator**
4. Click **Activate**
5. Enter reason + ticket number
6. Submit

📸 *Screenshot 3 — Activation request submitted (Pending approval)*

---

## **Step 4 — Approve Request (as Global Admin)**
1. PIM → Approve requests
2. Review Emma’s request
3. Approve with comment

📸 *Screenshot 4 — Approval screen*

---

## **Step 5 — Verify Active Role (Emma)**
1. Switch back to test user  
2. PIM → My roles → Active assignments  
3. Confirm **User Administrator — Active (1 hour)**

📸 *Screenshot 5 — Active role status*

---

## **Step 6 — View Audit Logs**
1. PIM → My audit  
2. Filter by role = User Administrator  
3. Review:
   - Assignment  
   - Activation  
   - Approval  
   - Update  
   - Expiration  

📸 *Screenshot 6 — PIM audit logs*

---

# 🏁 Final Output / What I Learned

### ✔ How PIM prevents permanent admin access  
### ✔ How JIT (“Just-In-Time”) access works  
### ✔ How to configure MFA, approval, justification  
### ✔ How users request and activate privileged roles  
### ✔ How admins approve or deny privileged access  
### ✔ How to read PIM audit logs  
### ✔ Why PIM is essential for Zero Trust architecture  
### ✔ Real-world scenario used by enterprises and IAM teams  

---

# 📚 Skills Demonstrated (IAM Focus)
- Microsoft Entra Identity Governance  
- Privileged Identity Management (PIM)  
- Just-in-Time role activation  
- Access approval workflows  
- Conditional access security layering  
- Zero Trust administration  
- Privileged access auditing & monitoring  
- Incident prevention through least privilege  

---

