## Pega Express Delivery Approach
### Terminology
 - **Pega Platform** - Pega's set of tools to build applications *facilitating customer interactions*
	 - *These interactions are referred to as* ***journeys***
 - **Pega Express** - An Agile approach, utilizing Pega's opinionated design to quickly deliver a pleasing application that accomplishes a business task, aka the **Minimum Lovable Product (MLP)**
 - **Microjourney** - A small part of the customer journey, focused on accomplishing a specific goal
	 - E.g. changing an address - journey starts with the request, ends in the updated records
 - **Personas** - Specific user needs personified, e.g. a customer/employee
 - **Channels** - The means by which a persona interacts with an application, e.g. a webpage/chatbot
 - **Data** - The information the ***Microjourney*** interacts with, e.g. an address record
 - **Interface** - Where the ***data*** comes from or where it is persisted

```
In the Address change Microjourney, a customer service agent walks the customer through the process of changing their address. The customer service agent and the customer access separate Web Portals. Drag the following items to the appropriate drop zone.
```
The *Customer* and the *Customer Service Agent* are **Personas**, and the *Customer Web Portal* and *Agent Web Portal* are **Channels**.

```
Consider a Postal address verification Microjourney. In this Microjourney, customers enter their mailing address in a Web Portal, and Pega Platform verifies whether the mailing address is valid by using the Postal Service database. Drag the following items to the appropriate drop zone.
```
The **Persona** is the *Customer*, the **Channel** is the *Customer Web Portal*, the **Data** is the *Mailing Address*, and the **Interface** is the *Postal Service*.

## Case Life Cycle
*Pega describes application flow similar to how a business would - e.g., you **a customer submits an order**,  **the order is processed**, and then **the order is delivered**.*

## More Terminology
 - **Case Type** - A repeatable business transaction, e.g. *printing*, *shipping*, etc.
 - **Case** - A specific transaction instance which has an identifier, e.g. *Order #66*
	- Each time a user submits an order, **Pega Platform** creates an instance of an **Order Case** - that **Case** is then assigned a number
- **Case Life Cycle** - A representation of the business model of the **Microjourney**, comprised of:
	- **Stages** - Represents a step in the **Case Life Cycle**, e.g. *processing* or *delivery*
	- **Processes** - Contains the **Steps** that users complete as they work on the case
	- **Step** - An *action*, performed by a user or automation, working to complete the **Process**

```
Which two statements are true? (Choose Two)

A - A Case Type is an abstract model of a business transaction.
B - A Step is an Action or Task performed by the system or users.
C - A Case Type is an instance that represents work that delivers a meaningful outcome.
D - Processes contain a series of Stages.
```

*Answer: A & B*

## Case Life Cycle Design
**Cases** have 3 general stages in the **Case Life Cycle**:
 - **Create Stage** - Where all relevant data is gathered, must start first
	 - E.g. collecting user's address, payment info, and order details
 - **Primary Stage** - Stages that lead to an expected outcome - a majority of **Cases** usually belong to this stage
	 - E.g. building or retrieving order items, packaging, putting on a truck for delivery
 - **Resolution Stage** - Behavior that concludes the **Case Life Cycle**, *can have multiple of these!*
	 - E.g. order delivered and receipt is sent
	 - Alternatively: incorrect address, send notice email

**Stage Transitions** - How a **Case** moves from one **Stage** to another
 - Can be set to *Automatically transition*, *Wait for user action*, or to *Resolve the case*
 - There's a *Change Stage Step* as well

## Multi-step Forms
*There can be a lot of paperwork associated with online work - **Multi-step Forms** are guided, single-user assignments using multiple screens, called **Views**.*

**Views** - The different pages of a form.
 - There's multiple navigation styles - all generally feature *Next* and *Back* buttons, ending in *Submit*



## Draft Mode
*When creating a **Case Type** in App Studio, all **Processes** are created in **Draft Mode** - allowing you to quickly run the **Case Type** to check the flow and behavior.*

***Draft Mode** must be turned off before production use to prevent a **Guardrail violation** - **Guardrails** are essentially best practices used to prevent issues during production.*

*If there are no errors in your **Case Type** when saving, Pega will automatically switch off **Draft Mode**.*
