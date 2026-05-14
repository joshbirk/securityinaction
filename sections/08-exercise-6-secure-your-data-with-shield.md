[← Exercise 5: Fix Remaining Risks (Optional)](07-exercise-5-fix-remaining-risks-optional.md) | [Project Home](../README.md) | [Appendix: Standard Baseline XML →](09-appendix-standard-baseline-xml.md)

---

# Exercise 6: Secure Your Data with Shield

### Scenario

Your company is preparing to launch a high-stakes international expansion. This involves handling sensitive metadata, executive contract details, and private financial agreements. Leadership is concerned that over-privileged admins or curious users might access this data undetected, or that sensitive information might be hiding in plain text in unexpected fields.

Admins can secure their Salesforce data with Shield, a suite of add-on products that includes the ability to encrypt data at rest, monitor events including user activity, get a comprehensive audit trail of changes made to your data, and identify sensitive data in the wrong place. Shield also includes Data Detect where we can find any sensitive data that doesn't belong.

#### PII Information

**PII (Personally Identifiable Information)** is any data point that can be used to uniquely identify, contact, or locate a specific individual. Think of it as a digital fingerprint: it is the data that says, **"This record belongs to this exact person."**

Storing sensitive data like Social Security Numbers or home addresses within Salesforce creates a significant security responsibility. If these fields are linked to a record without proper safeguards, you risk leaking a person's private identity to anyone with access to that record. As an Admin, your goal is to ensure that while the *system* knows who the person is, the *users* only see the specific identifiers necessary for their job.

These are the highest-risk fields. If these are leaked, the individual's identity is compromised immediately.

* **Government IDs:** Social Security Numbers (SSN), Driver's License numbers, Passport numbers, and Taxpayer IDs.
* **Financial Data:** Credit card numbers, bank account numbers, and debit card details.
* **Contact Info:** Full legal name, home address, and personal cell phone numbers.

### Step 1: Create a Policy in Data Detect

Before you scan your data, you have to know where it is.

1. Open the **App Launcher**
2. Type *Shield* into the search bar

![](../assets/images/image40.png)

3. Click **Shield**
4. Click **Manage Policies** in the *Data Detect* window

![](../assets/images/image41.png)

5. Click **New**

![](../assets/images/image42.png)

6. Enter the following values into your policy

| Field | Value |
| :---- | :---- |
| Policy Name | PII Detection Policy |
| Description | Detect potential PII in standard CRM records |
| Date Range Start | 01/01/2026 |
| Date Range End | (Select Today's Date) |
| Compliance Category to Exclude | PII |

7. Click **Save**
8. Click **Add Object**

![](../assets/images/image43.png)

9. Select **Contact**
10. Check the box for *Social_Security_Number*
11. Click **Done**

![](../assets/images/image44.png)

12. Click Sensitive **Data Categories**

![](../assets/images/image45.png)

13. Click **Add sensitive data categories**

![](../assets/images/image46.png)

14. Click **+** next to Social Security Number

![](../assets/images/image47.png)

15. Click **Done**

### Step 2: Find the Risk Using Data Detect

1. Click **Run Scan**

![](../assets/images/image48.png)

2. Click Scan Policy

![](../assets/images/image49.png)

> **Tip:** Your scan will enter a queue. Move onto the next step—you can come back and check your scan status later by opening *Data Detect* and selecting **View Scan Results**.

Now that Data Detect has flagged the sensitive fields, you need to ensure that even if the underlying database were compromised, the data remains unreadable.

> **Further Reading:** [Experience Cloud Security](13-further-reading-experience-cloud.md)

---

[← Exercise 5: Fix Remaining Risks (Optional)](07-exercise-5-fix-remaining-risks-optional.md) | [Project Home](../README.md) | [Appendix: Standard Baseline XML →](09-appendix-standard-baseline-xml.md)
