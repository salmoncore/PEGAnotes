You can have lots of different types of users - some need different interfaces and features than that of the client or users. Pega has a **User Management** feature to help organize users into **Personas**, which can be assigned common application security settings and **Assignments**.

**Personas**

Under `Users -> User Management`, you can add a persona, and assign it to users.

![](attachments/Pasted%20image%2020250607223342.png)

**Channel Interfaces** are the user interface of Pega. Different **Personas** can be assigned different **channels**:

![](attachments/Pasted%20image%2020250607223521.png)

Additionally, each **Persona** can be given access to stages in the **Case Life Cycle**:

![](attachments/Pasted%20image%2020250607223611.png)

To manage **users**, or those who interact with the app, you can head to `Users -> User management -> People`.

![](attachments/Pasted%20image%2020250607223828.png)

Remember, a **persona** defines who the user *is*, while the **role** dictates what the user *can do*.

---

## Quiz Notes

![](attachments/Pasted%20image%2020250607223933.png)
  - Creating a Role - **configuration-level tasks**
	 - Supplying a channel defines the context in which the role operates (web, mobile, etc.)
	 - Supplying a name gives an identifier.
 - Creating a User - **done by IT staff for an individual**
	 - Users need a role to define permissions
	 - Users will more likely need an email supplied here, rather than during role creation

![](attachments/Pasted%20image%2020250607224552.png) 
- You need the channel before making the Role
- The Role defines the user type's permissions
- Adding the email address is giving a user a unique identity for the role to be assigned to
- The auditor can then linked to the auditor account

![](attachments/Pasted%20image%2020250607225108.png) 
 - A **role** represents a specific set of permissions - this is the only option where a role would be necessary to do what is asked