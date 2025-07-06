## Decision Tables in Dev Studio

**Decision Tables** are used to test property values against a set of conditions, and return appropriate outcomes.
 - App Studio provides decision tables for simple field calculations, while Dev Studio has more advanced capabilities.

You can **Delegate decision tables** to business stakeholders (**process owners**), allowing them to update rules (*like thresholds or conditions*) **without** developer intervention.
 - Makes adjusting values to meet business needs easier for citizen developers

**Returning Defaults**
 - By default, the system stops evaluation in a **decision table** once it finds a matching condition
 - *Evaluate all rows* allows every row to be checked
	 - Useful for scenarios requiring multiple outcomes
 - You can define or expand the list of allowed results in the **Results tab**

**Flow Processing**
 - Decision tables can dynamically guide a case's path using the **Decision Shape** in a flow
	 - Reminder that a **flow** is comprised of decision shapes and connectors, visually representing the path a case takes based on conditions and outcomes
 - Assignments can be routed to users or work queues based on **decision logic**

![](attachments/Pasted%20image%2020250619180853.png)

## Decision Trees

**Decision Trees** are used to evaluate multiple test conditions and return a result.
 - Ideal for scenarios with "branching" logic:

![](attachments/Pasted%20image%2020250619181004.png)

***Like* a decision *table*, decision *trees* consist of a set of values to evaluate, and results to return.**

***Unlike* a decision *table*, decision *trees* consist of a series of branches, each with increasingly specific conditions, eventually leading to a return value.**

**Branches** include:
 - A comparison value
 - A comparison operator (e.g. =, >, !=, etc.)
 - An action (e.g. return a result, continue, or stop)

**Nested conditions** can represent more specific logic.
 - An approval process can check both purchase amount and submitting department, evaluating the second **only** if the first condition is met.

![](attachments/Pasted%20image%2020250619181812.png)

## Decision Tree or Decision Table

![](attachments/Pasted%20image%2020250620143433.png)
**Decision Tables** evaluate many combinations of the *same property or condition*.
 - Use when working with repeatable criteria (e.g. employee evaluations for bonuses)
 - Each **column** evaluates the same property/operator pair
 - Use when dealing with **many similar properties**

![](attachments/Pasted%20image%2020250620143444.png)
**Decision Trees** evaluate *different properties* in a nested structure.
 - Use when working with varied criteria (e.g. assigning rewards based on multiple achievements)
 - Each **branch** evaluates a unique property, which can lead to further conditions
 - Use when dealing with **many conditions**

Note that **Decision Trees** and **Decision Tables** can't be used interchangeably for everything within Pega - 
 - **Trees and Tables** can be used for:
	 - Flow rules
	 - Expressions
	 - Activities
	 - Routers
- ONLY **Tables** can be used for:
	- Cascading approvals with an authority matrix

![](attachments/Pasted%20image%2020250620134752.png)

## Decision Rule Conflicts

**Conflict Tests** detect redundant or **unreachable** conditions in **Decision Tables** or **Trees**. 
 - E.g. if 'Credit Score > 1000' is placed below 'Credit Score > 900', the higher condition will *never be evaluated*
 - **Conflict tests** are skipped if *Evaluate all Rows* is enabled
 - A rule without overlaps like this is considered ***consistent***

**Completeness Tests** detect **missing** conditions or branches that can lead to gaps in decision logic.
 - Pega can suggest additional rows to cover all value combinations
 - Useful for when properties have multiple possible values (e.g. customer levels like Bronze, Silver, Gold)
 - The *Show Completeness* option can generate a lot of suggestions, so be careful determining which are relevant

---

## Quiz Notes

![](attachments/Pasted%20image%2020250620143534.png)
 - Refer to the image of the **Decision table** above

![](attachments/Pasted%20image%2020250620143804.png)
 - Read carefully! *Just now noticing the image is probably wrong - whoops!*

![](attachments/Pasted%20image%2020250620144031.png)
 - Remember - **Conflicts** check **unreachable conditions**, **completeness** checks **missing conditions**. 

![](attachments/Pasted%20image%2020250620144452.png)
 - Remember that **Decision tables** evaluate *many conditions*

![](attachments/Pasted%20image%2020250620144843.png)
 - Study. Remember that *otherwise branches* are a separate thing.