## Data Transforms and Default Values

**Data Transforms** convert data from one source's format/class into data that can be used with another format/class. 
 - They can be called within a **Process Flow**
 - Can be used to set **default values** for a property

**Dev Studio** -> Open a **Process** -> **Flow**
 - In the **Flow**, click the connector to open the properties window
 - Under **Set Properties**, select **Apply Data Transform**:
![](attachments/Pasted%20image%2020250610121500.png)

For a practical example, you can use a **data transform** to iterate over a list of items to copy the entities with a quantity greater than zero to sum up a price:

![](attachments/Pasted%20image%2020250610122047.png)

![](attachments/Pasted%20image%2020250610122053.png)

### Data Transforms for Default Property Values

The **Data Initalization** page updates `pyDefault` (an automatically created rule in Pega, used to set default property values when a new case instance is created), which in turn calls `pySetFieldsDefaults` (where basic field values are set when configuring views in App Studio).

You can access `pyDefault` and `pySetFieldDefaults` here:
![](attachments/Pasted%20image%2020250610123253.png)

In a scenario where `pyDefault` configurations had first and last name fields, it might look like this **Data Page**:
![](attachments/Pasted%20image%2020250610123448.png)

To reference the information, you need to add an entry to the **Pages & Classes** tab:
![](attachments/Pasted%20image%2020250610123627.png)

**Expressions** can be used when setting values in a **data transform**, for example:
![](attachments/Pasted%20image%2020250610123730.png)
 - `.DateofTravel` uses the **expression** `@CurrentDateTime()` to get the current date as its default value.

![](attachments/Pasted%20image%2020250610123904.png)
 - Note:
	 - The **Data initialization page** is for setting **static** default values for fields
	 - The **Visual data model** defines the structure and type of fields, **not initial values**
	 - The **`pyDefault` data transform** is for setting **dynamic defaults**, e.g. `@CurrentDateTime`
	 - The **`pySetFieldDefaults` data transform** is for setting **embedded property defaults**

## Superclass Feature

You can make **data transforms** more modular by using a **superclass**.
 - Allows you to combine several **data transforms**
 - Set values at multiple levels of the **class hierarchy**

![](attachments/Pasted%20image%2020250610143700.png)

When **superclasses** are used, Pega:
 - Identifies the parent of the next class
 - Goes up the hierarchy until the root parent class is found
 - Finds the data transform and invokes it

### Data Transform Superclass feature use case

Consider a *Claim* class with the following subclass structure:

 - Claim
	 - Home
		 - Rental

You can set **Data Transforms** so that common default values are set in the *Claim* class, and more specific values are found in the subclasses:

![](attachments/Pasted%20image%2020250610144506.png)

When rule execution is performed, the sequence is as follows:

![](attachments/Pasted%20image%2020250610144627.png)
1. *SetDefault* is called in the **Claim** class, which sets the *Date of Loss* and *Prefix* fields
2. *SetDefault* is then called within the **Home** class, which overrides the *Prefix* field and sets the *Address* field
3. *SetDefault* is called again in the **Rental** class to override the *Prefix* field again, and set the *Name on lease* field

![](attachments/Pasted%20image%2020250610145936.png)

### Configure the Superclass feature for Data Transforms

To configure the superclass feature in **Dev Studio**:
 - Create a **Data Transform** with the same name at each level
	 - Make sure to check the *Call superclass Data Transform* option on the data transform:![](attachments/Pasted%20image%2020250610150207.png)
 - If the properties are specified in both parent and subclass, the **Data Transform** in the subclass ***overrides*** the **Data Transform** in the parent class

![](attachments/Pasted%20image%2020250610150431.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250610150809.png)
^ Study this

![](attachments/Pasted%20image%2020250610151256.png)

![](attachments/Pasted%20image%2020250610151622.png)

![](attachments/Pasted%20image%2020250610151806.png)

![](attachments/Pasted%20image%2020250610151827.png)
