## Rules and Rule Types

`A Rule describes behavior of individual Cases.`

 - A **Rule** is an instance of a **Rule Type**, which defines the behavior of a Pega application.
 - **Pega has rules to describe the behavior for how the application should create, process, and resolve Cases.** 

Pega uses these rules to build the logic which defines the application's look, behavior, and process flow.

![](attachments/Pasted%20image%2020250609182745.png)

Using individual **rules** makes the application modular - by describing case behavior with narrowly-focused rules, you can combine and reuse the rules you create later.
 - E.g., if you create a rule to send an email with more rules defining the content, you'll only have to edit the rules defining the content if you want to change the message later.

There's 3 benefits to this modularity:
 - **Versioning**
	 - You create a new version of the rule whenever you need the Case behavior to change.
	 - This allows you to undo the change if needed.
 - **Delegation**
	 - Developers can delegate rules to business users so they can update the Case behavior as the business changes.
	 - Other parts of the application are unchanged while these rules are modified.
 - **Reuse**
	 - Rules can be reused whenever the existing case behavior is needed again.
	 - Otherwise, behavior can be reconfigured.

![](attachments/Pasted%20image%2020250609184515.png)

## Rulesets

To package **rules** for distribution, you collect them into a **Ruleset**. 

**Rulesets**:
 - Identify, store, and manage sets of rules
 - Can be thought of as an album, where a rule is a single song
 - Can be shared between applications the same way individual rules can

An instance of a **Ruleset** is called a **Ruleset Version**. When the contents of a **ruleset** are updated, a new version is made. Changes should only be made to the latest update of the **Ruleset version** - it's best practice to lock the older versions.

**Rulesets** are identified by names and version numbers.
 - If there was a ruleset called "*Expense*", you'd give it a major version, minor version, and patch number.
	 - *Expense:01-02-03*

Applications consist of a sequence of **rulesets**, which are called **Ruleset Stacks**.
- The stack determines the order in which Pega looks through rulesets to find the rule to use
- Each version of the application contains a unique Ruleset Stack
	- This allows for new versions of the application to reference newer ruleset stacks (and therefore access new features and functionality), while older versions can continue to reference the older ruleset stacks

**Best Practices**
 - For **Application Rulesets**, use names that are unique and make sense in a business context
 - For organization rulesets that are shared, begin the ruleset with a phrase that describes your company and business purpose - avoid acronyms
 - Don't use Pega in the name, or as a prefix - these are restricted for the Pega platform
 - Avoid using spaces in ruleset names, keep the length under 32 characters, and avoid using special characters
 - Refactor the ruleset to its own application, only share the base ruleset when sharing rulesets across applications
 - Develop upon the newest ruleset
 - Increment rulesets frequently to track changes over time
 - Create a new ruleset with a top-level class that inherits from `@baseclass`

![](attachments/Pasted%20image%2020250609194323.png)

## Rule Creation

In **App Studio**, rules are created automatically in the **Application Rules Layer**. By building in App Studio, the application rule creation process includes preset defaults, and therefore minimizes issues and errors related to rule creation.

Note that when you...
-  Add a new **case type** in App Studio...
	- It creates underlying rules which are available in both App and Dev Studio
- Add a **mobile channel** to the application...
	- It creates new rules in Dev Studio (in the Data-Portal class)
- Add a new Process in App Studio Case Manager...
	- It creates a new **Flow Rule** in the Pega application
- Add a View in App Studio...
	- It creates a **Section Rule** in Dev Studio, and sets the required Class Context
- Add a new data object using the Data explorer in App Studio...
	- It creates Data Pages based on the type and source of the data object

When you need more control over how a rule is created and reused you can **create rules in Dev Studio**.
 - **Dev Studio** uses the term **records** to refer to **rules**, properties, and other objects in **Pega**.
	 - When creating a **Rule** in **Dev Studio**, the **New Record** form prompts you to provide:
		 - **Rule Type** - The function, e.g. is this a report definition, field value, data type, or flow action?
		 - **Ruleset** - Specifies which ruleset to organize the rule into
		 - **Apply to** - Specifies what class the rule applies to
		 - **Label** - Specifies the name you want to use
	- These four pieces of information identify the **rule** within the application, and allows it to be found through **Rule resolution**.
		- **Rule resolution** is what allows Pega to find the appropriate rule to run

An **Instance Key** is used to identify each **rule** on the system.
- The **Instance Key** is created using a variety of information, including the internal name for the Rule, the identifier, the time it was created, and the class it applies to.

### Rule Creation Methods

New **Rules** can be created in **Dev Studio** via the **New Record form**. 
 - How you create the rule determines how much information is automatically entered
 - Some rules created in Dev Studio can be used in App Studio, depending on the Rule type

You can make new rules from:
 - The **Create** menu
 - **App Explorer**
 - Create a rule from a **Rule Reference**
 - Opening an existing rule and clicking *Save as*
 - The **Records Explorer**

*Note that all of these methods have different information that is automatically added to the rule, refer [here](https://academy.pega.com/topic/rule-creation/v7/in/72681/72701#:~:text=The%20following%20table%20describes%20some%20Rule%20creation%20methods%20and%20identifies%20the%20information%20specified%20on%20the%20New%20Record%20form%3A) for more information.*

![](attachments/Pasted%20image%2020250609203000.png)

## Classes and Class Hierarchy

Pega groups **Rules** into **classes** ***according how reusable they are***. There are three class types:
 - **Work class** contains **rules** that describe how to process cases (e.g. processes, data elements, and user interfaces)
 - **Integration class** contains rules that describe how the application interacts with other systems (e.g. how the app connects to an external database)
 - **Data class** contains rules that describe data in the application (e.g. customer data)

**Integration and Data classes are typically *reusable*, while work classes are meant to describe the behavior of a specific class - they're the most specific, and least reusable.**

*Note that these classes are chosen by Pega automatically.*

![](attachments/Pasted%20image%2020250609203509.png)

### Parent and Child Classes

A **class** can contain other classes - any class that contains other classes is a **parent class**, while any class that is contained by another is a **child class**. 
 - **Child classes** can inherit and reuse any of the rules that are defined for its parent class.

![](attachments/Pasted%20image%2020250609203746.png)

## Class Hierarchy

Classes are layered into a multi-level **class hierarchy** to organize the application, sorted from most-specific to least-specific. 
 - `The application can use any Rule that is available to an application through the class hierarchy.`
 - The name of each class identifies its position within the hierarchy - `TGB-IT-Work` denotes that `Work` is a child of the `TGB-IT` class, which is a child of the `TGB` class.

![](attachments/Pasted%20image%2020250609204202.png)

## Rule Reuse through Inheritance

`Inheritance allows your application to reuse existing Rules for other Cases or applications.`

There are two methods for rule inheritance - **pattern inheritance** and **directed inheritance**.

### Pattern Inheritance

**Pattern inheritance** is automatic, using existing class name structure to determine what rules are available for reuse.
 - This method searches classes that share a name prefix.

![](attachments/Pasted%20image%2020250609205713.png)
 - In this example, **ABCIns** is the parent to both the **Consumer** and **Business** child classes - they *inherit* from the parent, **ABCIns**.
	 - Changing something within PolicyProcessing on one side will not affect the other

### Directed Inheritance

`inheritance between classes where the parent class is explicitly specified`

If you want to reuse rules from outside the class hierarchy, this is how you can do that.

**Because Rules are aggregated based on whether they apply to all Cases or Cases of a certain type, directed inheritance promotes reuse based on whether a rule is appropriate for a specific function or task (the "functional suitability").**

![](attachments/Pasted%20image%2020250609212206.png)

## Inheritance and Rule Reuse

Pega searches for a rule first by:
1. Pattern Inheritance
	 - Checks the class of the case, moving up its **pattern inheritance hierarchy** (based on name structure)
 2. Then Directed Inheritance
	 - If the rule isn't found, Pega checks the class specified in **directed inheritance**, performing a new **pattern inheritance** search from the specified class
 - The process continues until the topmost class, `@baseclass` is reached
 - If the rule isn't found, Pega throws an error

![](attachments/Pasted%20image%2020250609212601.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250609213854.png)Remember that `Work` is part of the base class - pattern inheritance wouldn't work here, so it must be directed inheritance.
 - If the class name looks like `MyApp-Feature-Work`, the inheritance type is gonna be **Pattern inheritance**
 - If the class name looks like `Work-`, `Data-`, `Embed-`, etc, the inheritance type is going to be **Directed inheritance**

![](attachments/Pasted%20image%2020250609215838.png)
For the last two, remember that **integration** and **data** classes are very reusable (e.g. reusing a data object), while **work** classes might be very specific (e.g. 'Hiring' or 'Leave request')

![](attachments/Pasted%20image%2020250609220851.png)
Note that for inheriting from `@baseclass`, while it is the top of the class hierarchy, **it is not a part of the naming structure**. You **must** use directed inheritance to inherit from `@baseclass`.

![](attachments/Pasted%20image%2020250609221153.png)
Note that rules are handled automatically in App Studio based on the defaults it can work off of - while the rules *do* update their version numbers with each change, the name doesn't change. Definitely don't make them all manually, and remember that you can make new rules in Dev Studio that can be used in App Studio!

![](attachments/Pasted%20image%2020250609222237.png)
 - *TenantInfo* could go in either data spot, but makes much more sense under *LeaseMgmt* than on its own here
 - Remember that **Int** is short for **Integration** - used for things like API connections, and in this case, connecting to a third-party server
 - *BackgroundCheckHeader* is definitely best described by a UIPage
 - A flow rule is definitely best described as a **Work** flow