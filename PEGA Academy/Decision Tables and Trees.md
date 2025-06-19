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