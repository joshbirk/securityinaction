---
title: "Further Reading: Understand the Security Hierarchy"
nav_order: 11
---

[← Further Reading: Using the Audit Trail](10-further-reading-using-the-audit-trail.md) | [Project Home](../index.md) | [Further Reading: Session Based Problem Users →](12-further-reading-session-based-problem-users.md)

---

# Further Reading: Understand the Security Hierarchy

First, let's define the hierarchy of Salesforce security and Field-Level Security (FLS) permissions, ordered from the most restrictive foundational settings to the most granular and flexible extensions.

### 1. Organization-Wide Defaults (OWD)

* **The Foundation:** This is the "baseline" level of security. It defines the default visibility for records that a user does not own.
* **The Rule:** You always start with the most restrictive setting here (like "Private"). All other layers below can only **open** access; they cannot take it away.

### 2. Profiles

* **The "Home Base":** Every user must have exactly one profile. It defines the basic requirements for their job function.
* **The Role:** It grants standard Object permissions (Create, Read, Edit, Delete) and establishes the initial Field-Level Security (which columns they can see).

### 3. Permission Sets

* **The Additive Layer:** These are used to grant additional permissions to specific users without changing their profile.
* **The Role:** If a profile doesn't allow access to a specific field or object, a Permission Set can "give" that access to a subset of users who need it for a special project or task.

### 4. Permission Set Groups

* **The Administrative Bundle:** This is the highest level of organization. It allows admins to bundle several Permission Sets together into a single package.
* **The Role:** Instead of assigning 10 individual permission sets to a new hire, you assign one "Group" that contains all of them. This ensures consistency and simplifies user management.

These layers allow an admin to follow the Principle of Least Privilege by starting with the least permissive foundation (Org Wide Defaults) and layering in new functionality and access by building on top of profiles and organizing permissions into groups.

---

[← Further Reading: Using the Audit Trail](10-further-reading-using-the-audit-trail.md) | [Project Home](../index.md) | [Further Reading: Session Based Problem Users →](12-further-reading-session-based-problem-users.md)
