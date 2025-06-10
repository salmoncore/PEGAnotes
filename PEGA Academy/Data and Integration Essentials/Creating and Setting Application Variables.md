**Configuration Settings** give developers the means to customize parameters for application behavior.
 - Settings are organized into **Configuration Sets**
	 - These associate the setting with a common element, e.g. the application feature or a case type
 - **Configuration Settings** and **Configuration Sets** give low-code options for controlling application behavior
	 - Configuration settings reduce the need for **Rule overrides**
	 - Generally makes maintaining and updating apps easier
	 - Rule overrides introduce complexity, so it's best to use them sparingly

**Use Configuration Settings:**
 - To **Control the use of features in an app**
	 - Feature dependencies can be configured to be turned off until dependencies are met
	 - E.g. if your app needs to send an email at some stage and it's not configured, the **Configuration Setting** can disable the feature
 - To **Determine which Processes in a flow should be followed**
	 - E.g. if approval is needed based on a monetary limit, **Configuration Settings** can maintain the limit amount to allow for changes without modifying code
 - To **Control UI experience**
	 - **Configuration Settings** can control the display of instructions for a process, and can be used to hide instructions once processes have been adopted

![](attachments/Pasted%20image%2020250610155510.png)

Locate **Configurations** here, which contains settings for **Configuration Sets**.

## Development

**Configuration Sets** are created and maintained in **App Studio** - **Rules** such as classes, Data Pages, and Properties are created when developing **Configuration Sets**, and are visible in **Dev Studio**.
 - Configuration settings are Data Instances of the *Data-Configuration-Setting* class.\
 - Example **Configuration:**
![](attachments/Pasted%20image%2020250610155807.png)

Note that **Configuration Settings** use **Role-based Access Control** to grant access for different users.

**Configuration Sets** are defined in the *Pega-Configuration* class.
 - **Configuration Settings** are included when the **Include associated data** checkbox is selected during the product file creation: ![](attachments/Pasted%20image%2020250610160024.png)
 - There **must be an existing Configuration Set** to make a **Configuration setting**

To **Reference Configuration Settings** throughout the application, use the **Condition Builder**. 
 - **Condition Builder** has a menu to select the **Configuration Set** and **Configuration** settings:![](attachments/Pasted%20image%2020250610160228.png)

![](attachments/Pasted%20image%2020250610160245.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250610160415.png)

![](attachments/Pasted%20image%2020250610160619.png)
 - Note that *Changing the cost of an item* can be accomplished elsewhere

![](attachments/Pasted%20image%2020250610160849.png)
 - Remember that Role-based access control is supported