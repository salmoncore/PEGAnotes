In **App Studio**, you can configure **Validation Conditions** that perform a true/false comparison against a constant value or the value of a field.
 - More complex validation scenarios can require additional capabilities provided by **Validate Rules** in Dev Studio.

### Data Validation in Dev Studio

**Each of these examples requires behavior that is only configurable from Dev Studio**:
 - A Canadian customer must have their address formatted for Canadian postal codes.
 - An investor opening an investment account must complete a questionnaire to set their experience level.
 - Someone enrolling in healthcare must upload an information consent form.

**Validate Rules** - Ensure data that users provide meet certain conditions before continuing a case.
 - By assigning **Validate Rules** to **Flow Actions**, you can prevent users from entering info the application can't process, and therefore reduce processing errors.
 - **Dev Studio** can extend **Validate Rules** that are created automatically in **App Studio**, and can be used to create new **Validate Rules** in the Process category.

**Edit Validate Rules** - Compare the value of a property to a defined pattern.
 - E.g. an **edit validate rule** can check whether a property value consists of seven numbers, or has a space separating the third and fourth number.
	 - Note that **Edit Validate Rules** use **Java** to accomplish this functionality, and therefore can represent a security risk.
 - **Edit Validate rules** are performed on the client, but can be applied to a property by **referencing the Edit Validate Rule** on the Advanced tab of the property rule form, under **Use Validate**.

### Use Case:

You might need Business Logic to determine user input matches a certain format, e.g. for an address.
![](attachments/Pasted%20image%2020250610165332.png)
This **Edit Validate** rule ensures a postal code conforms to the US ZIP code format.

![](attachments/Pasted%20image%2020250610165529.png)

Another example would be checking the **Case Status** in order to have the application behave differently, depending on the stage it's in - this is accomplished with a **Validate** rule.

![](attachments/Pasted%20image%2020250610165752.png)
 - **Input Property** - Qualify Validation based on data provided by the user, e.g. experience level
 - **Proposed Work Status** - Qualify Validation based on the status the application applies to the case
	 - E.g. for a credit card, `Pending-Qualification` can be reached by a score of 600, while `Approved` can require a minimum score of 725
 - **Flow Action** - Qualify Validation is based on the action performed by the user
	 - E.g. If a user wants to run onboarding for a new employee, the start date must be in the future
 - **Stages** - Qualify Validation is based on the **stage of the case**
	 - E.g. During the `Submission` stage for a mortgage request, the user provides estimated income, but if in the `Approval` stage, the user must provide a confirmed value

![](attachments/Pasted%20image%2020250610170252.png)
 - An example of a **Validation Condition** for experience

![](attachments/Pasted%20image%2020250610170325.png)

*Note that true/false conditions can also be used for comparison in **Validation Rules***

![](attachments/Pasted%20image%2020250610170507.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250610170723.png)
 - All others can be configured in App Studio

![](attachments/Pasted%20image%2020250610170809.png)
- It uses Java!

![](attachments/Pasted%20image%2020250610171020.png)
 - Read carefully - we're looking for the option that prevents the user from *entering* an invalid combination. A Decision Rule or Validate/Edit Validate Rule might work, but it'd have to be assessed after the user already entered their information.