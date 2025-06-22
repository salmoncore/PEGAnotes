**Cascading Approvals** model a *sequence of approvals* based on either:
 - **Hierarchy** (the reporting structure)
 - **Customized Logic** (via an authority matrix)

For **Cascading Approvals**, think of examples like purchase requests or expense reports, which may require multiple approvals.

**Reporting Structure**
 - Follows organization's hierarchy
 - Approvals can escalate based on **thresholds** (e.g. higher expenses -> higher-level approval)
 - Configured in **Dev Studio** using an **approve/reject step**
	 - Use the **Cascading -> Reporting structure** option

**Authority Matrix**
 - More flexible, since it's not limited to managerial hierarchy
 - Includes approvals from external departments![](attachments/Pasted%20image%2020250620172719.png)
 - Uses a **Decision Table**, **Data page**, **activity**, or a **Data transform** to build the list of approvers
	 - Can be set to *Evaluate all Rows* to ensure that every conditionally required approver is included

![](attachments/Pasted%20image%2020250620172922.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250620173018.png)

![](attachments/Pasted%20image%2020250620173138.png)

![](attachments/Pasted%20image%2020250620173427.png)
 - Study - Remember that **decision tables** are used for the authority matrix model, *not* for the reporting structure model.

![](attachments/Pasted%20image%2020250620173637.png)

![](attachments/Pasted%20image%2020250620173727.png)

![](attachments/Pasted%20image%2020250620174451.png)
 - Question is essentially asking which option depends on a unique approver pattern, data reference, and a potential mix of different approvers that aren't linked in the hierarchy.