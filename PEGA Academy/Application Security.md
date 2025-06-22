## The Security Checklist

The **security checklist** is mandatory to complete before Pega applications are deployed - otherwise, the **deployment manager** blocks the release.

There's four critical security areas:
 - **Data Encryption**
	 - You can select the encryption type
	 - Encryption is used to protect:
		 - Passwords
		 - Properties
		 - BLOBs
		 - e.g. SSNs, credit card information, addresses, etc.
	 - Designed to comply with privacy policies, regulatory requirements, and contractual obligations
 - **Authentication**
	 - Ensures only users and verified systems can access the application
		 - E.g. a user using SSO, entering a username/password, or using an external identity provider
 - **Authorization**
	- Also called **access control**
	- Ensures that after logging in, a user only has access to the data they have permission to read or modify
	- There are three types of authorization:
		- Role-based access control
		- Attribute-based access control
		- Client-based access control
 - **Auditing**
	 - Also called **accountability**
	 - Allows you to view and track security events
		 - E.g. failed logins, password changes, changes to rules and data
	 - Allows you to meet security criteria

Ultimately, **it is up to Pega and the client to deliver a secure application**. The goal is to uphold the **AIC triad**:
- **Availability**
- **Integrity**
- **Confidentiality**

![](attachments/Pasted%20image%2020250621203415.png)

Pega automatically installs an **application guideline Rule instance** that includes the tasks in the security checklist for each version of the application.

**Guardrail compliance** - Pega stresses the importance of using built-in features rather than custom code, which might bypass security rules.

**Checklist tasks** - Categorized based on the timing (e.g. development, deployment, etc.) and focus areas (e.g. monitoring, authentication, authorization, auditing, and testing)
 - Not every task applies to every app
	 - Risk and feature usage guide what is needed

![](attachments/Pasted%20image%2020250621204001.png)

## Security Policies

Security should be addressed early in the application lifecycle - ideally in the **prepare** and **design** phases. Pega focuses on two key types of security:

**Application-level Security**
 - Prevents unauthorized access to the application
 - Involves tools like password policies, authentication methods, and third-party security integrations
 - **Goal:** Keep non-authorized users out entirely

**Feature Security**
 - Controls what authorized users can access within the app
 - Includes **Role-Based Access Control**, **Attribute-Based Access Control**, and **Client-Based Access Control**
 - Tailors access by user roles and personas; e.g. managers may view certain payroll data, but not edit it

![](attachments/Pasted%20image%2020250621204410.png)

**Security Policy Configuration**
Security settings are managed on the **Security Policies Tab** in App or Dev Studio.

**Frequently Required Policies:**
 - Password - set complexity and length requirements
 - CAPTCHA - add challenges to prevent bots
 - Lockout - define behavior after failed logins
 - Audit - track login attempts and security issues
 - MFA - require one-time passwords through email or SMS
 - Operator Disablement - auto-disabled accounts after inactivity

**Best Practices:**
 - Define security needs early on
 - Add security requirements to the project **Definition of Done**
 - Use the **Security Checklist** to ensure security coverage of the entire Pega application

![](attachments/Pasted%20image%2020250621204925.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250621205633.png)
 - Note that *Enable authentication lockout policy* refers to *progressive* lockouts, where the delay increases with each failed attempt

![](attachments/Pasted%20image%2020250621210104.png)
 - Note that the **guardrail compliance score** is on the *guardrails landing page*, and that the security tasks depend per application

![](attachments/Pasted%20image%2020250621210225.png)
 - 