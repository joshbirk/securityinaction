---
title: "Further Reading: Using the Audit Trail"
nav_order: 10
---

[← Appendix: Standard Baseline XML](09-appendix-standard-baseline-xml.md) | [Project Home](../index.md) | [Further Reading: Understand the Security Hierarchy →](11-further-reading-understand-the-security-hierarchy.md)

---

# Further Reading: Using the Audit Trail

### 1. The Setup Audit Trail: Tracking Policy Changes

This tool tracks "Who changed the security settings?" It is your best defense against accidental (or malicious) changes to your session security.

* **What it tracks:** Changes to MFA requirements, modifications to Login IP Ranges, and permission set assignments.
* **The Scenario:** You set up a strict Login IP Range for the "Waffles Over Everything" Org, but a week later, it's gone.
* **How to use it:**
  1. Go to **Setup > Security > View Setup Audit Trail**.
  2. Download the last six months of data as a `.csv`.
  3. **Search for:** Keywords like "Login IP," "MFA," or "Permission Set."
  4. **The Result:** You can see exactly which Admin deleted the IP range and at what time, allowing for a "post-mortem" coaching session.

---

### 2. Login History: Tracking Session Behavior

While the Setup Audit Trail tracks *policy* changes, the **Login History** tracks *user* behavior. This is where you find "Impossible Travelers" or credential stuffing attempts.

* **What it tracks:** Every login attempt (Success or Failure), the Source IP, the Browser/Platform, and the **Login Type** (e.g., Application, Service, or SAML for SSO).
* **How to use it to secure sessions:**
  1. Go to **Setup > Users > Login History**.
  2. **Filter by Status:** Look for "Invalid Password" or "Failed: IP Restricted." A high volume of these for a single user suggests a brute-force attack.
  3. **Check MFA Challenges:** Look for the "Identity Verification" status. If a user has 50 "Success" logins but 0 "Identity Verification" challenges, your MFA policy might not be applied to them correctly.
  4. **Identify Old Protocols:** Look for logins using outdated TLS versions or browsers. You can use this data to force users to upgrade for a more secure session.

---

### 3. Login Forensics: The "Advanced" Audit

For Admins who need more than just a list of IPs, **Login Forensics** (part of Event Monitoring) provides deeper insights into session security without needing a full Shield license.

* **The Benefit:** It doesn't just show *where* they logged in; it identifies **anomalies**.
* **What it spots:**
  * **Average Login Volume:** If a user typically logs in 5 times a day but suddenly logs in 500 times, the system flags it.
  * **Suspicious Timeframes:** Logins occurring at 3:00 AM for a user who only works 9-to-5.

---

[← Appendix: Standard Baseline XML](09-appendix-standard-baseline-xml.md) | [Project Home](../index.md) | [Further Reading: Understand the Security Hierarchy →](11-further-reading-understand-the-security-hierarchy.md)
