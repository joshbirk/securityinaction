---
title: Session-Based Problem Users
layout: default
parent: Further Reading
nav_order: 3
---

### **Further Reading: Session Based Problem Users**

### **1\. The "Zombie" User (Inactive but Alive)**

A Zombie User is a defunct account that was never properly deactivated.

* **The Scenario:** An employee leaves the company, but the Admin only disables their email. The Salesforce user record remains "Active."  
* **The Risk:** If the former employee can still access the network (or if their password is known), they can log in and export data. This is a massive compliance failure.  
* **The Indicator:** Users who are "Active" but haven't logged in for 90+ days.

### **2\. The "Orphaned" User (Integration/System Accounts)**

These are accounts created for a specific purpose—usually an integration, a consultant, or a temporary project—that no longer has an "owner."

* **The Scenario:** A consultant built a custom integration three years ago using a dedicated user license. The consultant is gone, the integration is deprecated, but the user account is still active and has "System Administrator" permissions.  
* **The Risk:** These accounts are high-value targets for hackers because they often have "God Mode" access and nobody is watching their login activity.  
* **The Indicator:** High-privilege accounts with no clear human owner or associated active project.

### **3\. The "Ghost" Admin (Admin Creep)**

This is when a user has "System Administrator" or "Modify All Data" permissions but doesn't actually perform admin duties.

* **The Scenario:** A Sales Operations Manager was given Admin access "just in case" during a busy implementation phase. Six months later, they still have it.  
* **The Risk:** Accidental damage. A "Ghost Admin" might inadvertently change a global picklist or delete a critical report while trying to do their daily job.  
* **The Indicator:** Users on the System Admin profile who haven't touched the Setup menu in months.

### **4\. Irregular Login Behavior (The "Impossible Traveler")**

This is a behavioral red flag that suggests an account has been compromised.

* **The Scenario:** A user logs in from New York at 9:00 AM, and then logs in from London at 10:00 AM.  
* **The Risk:** Credential sharing or account takeover.  
* **The Indicator:** Multiple failed login attempts followed by a success, or logins from unusual IP ranges/countries.  
* **The Tool:** This is where **Event Monitoring** becomes essential.

### **5\. "Shadow" Users (Shared Accounts)**

* **The Scenario:** To save on license costs, a small team shares a single "Sales User" login.  
* **The Risk:** Total loss of **Audit Trail**. If a record is deleted or data is stolen, you cannot prove *which* human did it. It also violates Salesforce's Terms of Service.  
* **The Indicator:** Concurrent sessions from different IP addresses on a single user record.
