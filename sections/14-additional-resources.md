---
title: Additional Resources
nav_order: 14
---

[← Further Reading: Session Based Problem Users](12-further-reading-session-based-problem-users.md) | [Project Home](../index.md)

---

# Additional Resources

## Salesforce Help

* [Security-Related Product Updates to the Salesforce Platform: User Identity, Data Protection, and Access Controls](https://help.salesforce.com/s/articleView?id=005317465&type=1)
* [Prepare for Phishing-Resistant MFA Enforcement for Privileged Users including Admins](https://help.salesforce.com/s/articleView?id=005321563&type=1)

## Salesforce Trust

This is the primary hub for transparency and security updates. It provides real-time information on system performance and security incidents.

* [**Trust.salesforce.com**](https://trust.salesforce.com/): View live status updates, planned maintenance, and security alerts.
* **Compliance:** Detailed documentation on global certifications (ISO, SOC, HIPAA, etc.).

## Salesforce Shield

[Shield Data Sheet](https://www.salesforce.com/content/dam/web/en_us/www/documents/platform/Shield-Datasheet.pdf) | [Shield Demo](https://www.salesforce.com/platform/conf/demos/shield-overview/) | [Webinar: Implement Shield in 20 Minutes](https://www.salesforce.com/events/webinars/implement-salesforce-shield-20-minutes/) | [Trailhead: Secure your Apps with Salesforce Shield](https://trailhead.salesforce.com/content/learn/trails/shield)

Shield is a suite of advanced security and compliance tools designed for organizations in highly regulated industries or organizations that store critical or sensitive data. It consists of four main components:

* **Platform Encryption:** Unlike standard encryption, this allows you to encrypt sensitive data at rest (fields, files, and attachments) while still maintaining platform functionality like search and workflow.
* **Event Monitoring:** Provides a "behind-the-scenes" look at user activity. You can track who is accessing what data, from which IP, and even see when someone downloads a report.
  * *New for 2026:* Automated Transaction Security Policies now proactively block suspicious report exports or logins based on AI-driven risk scores.
* **Field Audit Trail:** Extends your data retention capabilities. While standard Salesforce only tracks field changes for 18 months, Field Audit Trail can store up to 10 years of history for up to 60 fields per object.
* **Data Detect:** Uses managed data discovery to scan your org for sensitive information (like PII or credit card numbers) that might be stored in the wrong places, helping you categorize data for compliance.

## Security Center

[Datasheet](https://www.salesforce.com/content/dam/web/en_us/www/documents/platform/Security-Center-Salesforce-Datasheet.pdf) | [Demo](https://www.salesforce.com/platform/demos/security-center/) | [Trailhead](https://trailhead.salesforce.com/content/learn/modules/security-center) | [Web](https://www.salesforce.com/platform/security-center/)

If Shield is about *securing the data*, Security Center is about *managing the posture* across your entire ecosystem. It is essential if you manage more than one Salesforce org.

* **Single Pane of Glass:** View security health, configuration changes, and user permissions across all your production and sandbox environments in one dashboard.
* **Agentforce Integration (2026):** Security Center now includes AI-powered agents that flag "unusual activity"—such as a sudden spike in admin permissions or a login from a restricted geography—and suggest immediate remediation plans.
* **Policy Management:** Create a "security blueprint" and push it to all your orgs to ensure they all meet the same standards (e.g., ensuring MFA is enabled everywhere).

## Trailhead

Salesforce's free gamified learning platform offers specific "trails" for security.

* [**Protect Your Salesforce Data**](https://trailhead.salesforce.com/content/learn/trails/security-specialist-superbadge): Covers the basics of visibility and access.
* [**Security Specialist Superbadge**](https://trailhead.salesforce.com/content/learn/superbadges/superbadge_security): A real-world business case where you must implement complex security requirements to prove your proficiency.
* [**User Authentication**](https://trailhead.salesforce.com/content/learn/modules/user-authentication): Focused on Multi-Factor Authentication (MFA), Single Sign-On (SSO), and My Domain.

## Community & Best Practices

* [**Salesforce Admins - Security Page**](https://admin.salesforce.com/topics/security): Blog posts and webinars specifically for admins on how to simplify security.
* **Trailblazer Community:** Groups like **"Security Group-Public"** allow you to ask questions to Salesforce employees and experienced MVPs.

---

[← Further Reading: Session Based Problem Users](12-further-reading-session-based-problem-users.md) | [Project Home](../index.md)
