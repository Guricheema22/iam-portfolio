# 🔐 Lab 11 – Access Reviews for M365-Business-Users Group

## 🎯 Objective
In this lab, I configured an **Access Review** in Microsoft Entra ID to ensure only the correct users retain access to the *M365-Business-Users* group.  
Access Reviews help organisations prevent privilege creep, maintain compliance, and enforce least-privilege access.

---

## 📌 Why Access Reviews Are Important (Simple Explanation)
In enterprise environments, **groups = access**.

Being in a group gives a user access to:
- Applications (Salesforce, ServiceNow, HR systems)
- SharePoint sites & Teams channels
- Admin permissions
- Sensitive business data

Over time, people change roles — but their access often stays the same.

This causes **privilege creep**.

Access Reviews automatically notify managers or reviewers at regular intervals to check:

> “Does this person still need access?”

This ensures:
- Access stays clean
- Inactive users are removed
- Guest users do not retain long-term access
- Organisations stay compliant (ISO, SOC2, Essential Eight)

---

## 🛠️ Lab Tasks Performed

### 1️⃣ Open Identity Governance → Access Reviews
- Navigated to **Microsoft Entra Admin Center**
- Opened **Identity Governance**
- Selected **Access Reviews**
- Clicked **New Access Review**

---

### 2️⃣ Select Review Type
- Chose **Teams + Groups**
- Review target: **M365-Business-Users**
- Scope: **Everyone** (all members)

---

### 3️⃣ Configure Reviewers
- Reviewer: **Myself (Gurvinder Cheema)**
- Review method: **Selected users**
- Duration: **3-day one-time review**
- Start date: **05/02/2026**

---

### 4️⃣ Configure Settings
- Require reason when approving/denying → **Off** (optional)
- Auto-apply results → **Enabled**
- If reviewer doesn’t respond → **Remove access**
- Notify reviewers → **Enabled**
- Send reminders → **Enabled**

---

### 5️⃣ Review + Create
Review name: Lab 11 – Access Review for M365-Business-Users Group



Created the Access Review successfully.

---

## 📊 Lab Results

### ✔ Access Review Status
- Review period: **02/05/2026 – 02/11/2026**
- Group members: **3 users**
- Automated recommendations displayed:
  - Users with no recent activity → **Deny**
  - Active user → **Approve**

---

## 📥 Reviewing Access via MyAccess Portal
Opened reviewer portal: https://myaccess.microsoft.com/


Performed decisions:

- John Smith → **Deny**
- Admin-One → **Deny**
- Emma Brown → **Approve**

Submitted the review.

Access review status updated to **Completed**, and denied users will be removed automatically.

---

## 🧠 What I Learned
- How to configure Access Reviews in Entra ID  
- How to manage least-privilege access over time  
- How Access Reviews prevent **privilege creep**  
- Why scheduled reviews are required for compliance  
- How inactive, external, or over-privileged accounts get detected  
- How auto-apply ensures denied access is removed instantly  

---

## 📚 Real-World Example
A user moves from **Finance → Marketing**, but still remains in the **Payroll-Access** group.

This creates risk.

An Access Review notifies the Finance Manager:

> “Does this user still need payroll access?”

Manager selects **Deny** → Access is automatically removed.

This is how companies stay secure and audit-ready.

---

## 📸 Screenshots (Added in evidence order)
01-access-review-dashboard.png
02-select-group.png
03-reviewer-settings.png
04-review-summary.png
05-myaccess-review.png
06-decisions.png
07-review-completed.png


---

## 🏁 Lab 11 Completed
This lab demonstrates practical experience with **Identity Governance**, **Access Reviews**, **least privilege**, and **compliance workflows** — essential skills for IAM Analyst and Cloud Security roles.


