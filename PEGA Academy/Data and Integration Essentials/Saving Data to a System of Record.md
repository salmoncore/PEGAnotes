## Savable Data Pages

**Savable Data Pages** can be used to save a page or list of page data to a **system of record (SOR)**.
 - The **system of record** can be the **Pega platform**, or something like an external database.
 - Using **Savable Data Pages** allows you to update the **SOR** in real-time with **case** data, and can manage the transaction to handle data synchronization in the event of some error, like a network outage.

The **data save plan** details how saving **savable data pages** is performed, e.g. by specifying *when **rules*** that determine when an option is used. Options include:
 - **Database save** - Saves a single page of data to a single row in the system of record
 - **Activity** - Calls an Activity to save the data, can be used to access a connector for pages managed by an external SOR or a Pega database. Limit using activities when possible.
 - **Connector** - Saves and persists data to an external SOR using a REST connector
 - **Robotic Automation** - Uses a Robotic Process Automation to write data to a SOR
 - **Robotic desktop Automation** - Uses a Robotic desktop Automation to write to a SOR

When using **Savable Data Pages**, you can write data to the SOR using Pega's transaction handling.
 - Transaction handling allows for the system to be responsive to errors
 - E.g., if a credit card transaction is handled, the payment and payment notification in performed in the same transaction. In the event of a failure in payment processing, the changes to both systems roll back to the state from before the order - your card isn't charged, and the order is not processed.

You can trigger the save plan for a **savable data page** by:
 - Adding a **Save Data Page** automation step in a flow Rule
 - Adding post-processing for a Flow Action Rule
 - Calling the *Save-DataPage* method in an activity Rule

![](attachments/Pasted%20image%2020250618190703.png)

**Auto-populated Properties** are Page or Page List properties that automatically fill themselves with data pulled directly from **data pages** to simplify maintenance and improve performance.
 - You can auto-populate properties by:
	 1. Referencing a data page - **a live link to data** (be careful - this can lead to an accidental data overwrite before the save is triggered)
	 2. Copying data from a **Data Page** - takes a snapshot of the data (recommended for **savable data pages**)

![](attachments/Pasted%20image%2020250618202520.png)

If you're just trying to update information instead of updating the entire data object, use the **Update Details Action**.

**Savable Data Pages** can be configured with multiple data sources, each with **their own data save plan**, which can support creating and updating Data Records.
 - Note that specifying the key value as **optional** instead of required may be required when configuring data pages that support both create and update operations - otherwise, you may encounter an error preventing saving.

![](attachments/Pasted%20image%2020250618203336.png)

## Save Data Page Automation

You can send data from a **Data Page** to a **System of Record** using a **Savable Data Page**.
 - After adding a *Save Plan* to a **Data Page**, add a **Save Data Page** automation step to the Case Life Cycle to identify when Pega should update the SOR.

Using a **Save Data Page** within a **flow Rule** allows you to save data, such as an Assignment, back to a System of Record.

![](attachments/Pasted%20image%2020250618204314.png)

**Save Data Page**'s automation allows for two options:
 - Enter the **Data Page Name** to be used
 - Select **Use associated property** and enter or select a **page or page list**

![](attachments/Pasted%20image%2020250618204550.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250618204732.png)

![](attachments/Pasted%20image%2020250618204809.png)

![](attachments/Pasted%20image%2020250618204827.png)