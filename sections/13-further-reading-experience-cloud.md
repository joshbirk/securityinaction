---
title: "Further Reading: Experience Cloud Security"
nav_order: 13
---

[← Further Reading: Session Based Problem Users](12-further-reading-session-based-problem-users.md) | [Project Home](../index.md) | [Additional Resources →](14-additional-resources.md)

---

# Further Reading: Experience Cloud Security

Experience Cloud is a unique security risk because it serves as a bridge between your private, internal Salesforce data and the public internet. While standard Salesforce security focuses on internal employees, Experience Cloud introduces **External Users** (customers and partners) and **Guest Users** (anonymous public visitors), creating a much broader "attack surface."

### Why it is a Unique Risk

The primary risk stems from the **Shared Responsibility Model**. While Salesforce secures the infrastructure, the Admin is responsible for the "Sharing Model." Because Experience Cloud can bypass some standard internal protections to facilitate external access, a single misconfiguration can turn a helpful customer portal into an open gateway for hackers.

### Overview of Key Risks

According to the [Salesforce Security Documentation](https://help.salesforce.com/s/articleView?id=experience.networks_security.htm&type=5), the primary vulnerabilities include:

* **Over-Permissive Guest Profiles:** Guest users (people who aren't logged in) may inadvertently be granted "Read" or "View All" access to sensitive objects.
* **Aura/API Exploits:** Malicious actors often use tools (like Aura Inspector) to probe public-facing API endpoints. If "API Enabled" is checked on a guest profile, they can query your data directly.
* **Insecure "Internal" Defaults:** If your Org-Wide Defaults (OWD) are set to "Public" internally, they may leak to the external site unless the **External OWD** is explicitly set to **Private**.
* **Clickjacking:** Attackers can use iframes to trick your portal users into clicking malicious links that appear to be part of your trusted site.
* **Member Visibility:** Default settings may allow customers from different companies to see each other's profiles and contact info, leading to a significant privacy breach.

### Summary of Best Practices

To mitigate these risks, Salesforce recommends a **"Zero-Trust"** approach:

1. **Restrict Guest Access:** Ensure Guest User Profiles have the absolute minimum permissions.
2. **External OWDs:** Always set Default External Access to **Private**.
3. **Disable Public APIs:** Uncheck "API Enabled" and "Allow guest users to access public APIs."
4. **Clickjack Protection:** Enable "Allow framing by the same origin only" in your site settings.

For more detailed implementation steps, refer to the official documentation:

[Secure Your Experience Cloud Site - Salesforce Help](https://help.salesforce.com/s/articleView?id=experience.networks_security.htm&type=5)

---

[← Further Reading: Session Based Problem Users](12-further-reading-session-based-problem-users.md) | [Project Home](../index.md) | [Additional Resources →](14-additional-resources.md)
