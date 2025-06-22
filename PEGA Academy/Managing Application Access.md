## Application Access

**Personas**
 - Define the business context of a user
**Roles**
 - Outline specific tasks a user can perform in an application

**Channel Interfaces**
 - Each role has a default channel interface (like Doctor Portal vs Patient Portal, also referred to as a *user interface*)
 - The default channel interface determines the screen shown at login

**Role Based Access Control**
 - RBAC is used to manage app security by assigning roles with specific permissions.
 - Combines *authentication* (verifying user identity) and *authorization* (controlling data/action access)

**Access Roles and Access Groups**
 - Access **roles** group users by job function
	 - E.g. manager, user, etc.
 - Access **groups** contain one or more access ***roles*** and manage overall privileges
	 - If a conflict arises from the role, the most permissive rule applies

Note that RBAC is one layer of protection - still need to refer to the security checklist.

![](attachments/Pasted%20image%2020250621211756.png)
 - Read carefully - the **group** is comprised of ***all the roles***

## Access Control

**User Management Controls**
 - In *App Studio*, you can configure most access control settings
 - In *Dev Studio*, you can access advanced permissions, like deleting case instances via the **access manager**

**Types of Access Records**
 - ARO (Access of Role to Object)
	 - Grants or denies permissions for specific classes and roles
 - Access Deny
	 - Explicitly denies access, even if an ARO permits it
		 - Useful for ensuring a role *cannot* access something

Use the **Persona Access Landing Page** or **Access manager** instead of editing the rule forms directly - it's better for maintainability

**System-Level Access Control**
 - Tied to **production levels** (0-5)
	 - 0 = *denied*
	 - 1 = *Sandbox*
	 - 2 = *Development*
	 - 3 = *QA*
	 - 4 = *Staging*
	 - 5 = *Production*
 - Permissions are only granted if the user's access level => the system's production level
	 - E.g. A user at level 2 can access a sandbox, but not production

The **Access Manager** reflects access based on the environment

![](attachments/Pasted%20image%2020250621212716.png)

---
## Quiz Notes

![](attachments/Pasted%20image%2020250621212949.png)
 - Review this - personas are used to easily assign permissions to a type of user like this

![](attachments/Pasted%20image%2020250621213136.png)
 - Operator ID -> User
 - Operator Record -> belongs to what Access Group
 - Access Groups -> permissions originated from Access Roles

![](attachments/Pasted%20image%2020250621213247.png)