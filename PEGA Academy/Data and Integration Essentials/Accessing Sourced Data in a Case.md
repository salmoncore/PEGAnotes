## Data Pages

Case processing often requires data that is sourced from other applications or systems. To prevent issues in accuracy from externally-sourced data, **Data Pages** can be used to manage the integration of the data source.
 - **Data Pages** retrieve data from a source, and caches the data in memory
 - The application can be developed without knowing the data source and connection details

### On-Demand Data Access

While most Pega pages are populated through explicit actions when accessed, **Data Pages** specifically are designed to load their content only when they are accessed, making them a type of "declarative rule" within the Pega Platform.
 - Pega automatically adds the prefix `D_` to the name of **data pages** to differentiate them from other types of pages in memory

**Data Pages** work in this manner:
1. They're first defined by a developer, including the type, structure, and source of the data
2. A user then requests data from a data page
3. Pega attempts to check whether the data is present in memory
4. If the data isn't cached in memory or is outdated, Pega queries the data source specified
5. Data is returned from the data source to the system...
6. ...which is then returned to the user to fulfill the data request

![](attachments/Pasted%20image%2020250610230153.png)

## Data Page Definition

In **Dev Studio**, you can create **Data Pages**, which consist of:
 - The **structure** the of the page contents
	 - The **Structure** of the data page determines whether the data page contains one (**page**) or many (**list**) items, and can be set by an option in the **Structure** drop-down list
	 - `<DataPageName>.pxResults(<index>)` is the syntax to access a specific record within a data page's list of data
 - The **object type** represented by the contents
	 - **Object type** can be set by entering the **class** of the object
	 - Setting the **object type** allows Pega to reference properties defined by the class
 - The **edit mode** which is supported
	 - The **edit mode** indicates how or if an application can manipulate the information on a **data page**
		 - **Read only** mode prevents the app from updating the **data page**, except when loading and updating the contents from the data source. This prevents the data always matches the content on the external source.
		 - **Editable** allows the app to edit the **data page** contents (**NOT** saving the information back to the data source, **just** the **data page**).
		 - **Savable** allows the application to push data *back to the **data source***. The app follows the **save plan** to connect to the customer database and make the update.
 - The **scope** of the data page
	 - Determines the **visibility** of the **data page** contents within the app, following one of the following options:
		 - **Thread** ensures the contents of a **data page** are unique to a single **case**, e.g. a single transaction has the product info isolated to the one order
		 - **Requestor** should be used if the contents of the data page need to be accessed by a single user or system, e.g. a single customer or system can choose a saved location for a new order
		 - **Node** is used if all users and systems can share the data page, e.g. sellable product information that can be used by all systems for consistency in selling

![](attachments/Pasted%20image%2020250611183133.png)
## Data Sources

The **data sources** section of the **data page** form specifies how Pega populates the content of a **data page** when the application refresnces the page.

*To configure a **data source**:*
 - Specify **type of source**
 - Specify **name of data source**

*The following options can be used to configure the data source:*
- Data transform
- Activity
- Connector
- Report definition
- Database lookup
- Robotic automation
- Robotic desktop automation
- Aggregate sources
- Lookup

![](attachments/Pasted%20image%2020250611185711.png)
This is an example of a data source configured to populate a **data page**. 

 - Note that if you want to combine multiple sources to populate a data page, you should select **aggregate sources**, and identify each source to query.
 - Additionally, you must specify at least one data source - if the **data page** contains more than one, a logical condition for each source should be used to determine whether to query that data source.
 - You can use **parameters** to limit the contents retrieved to the **data page**, such as a key value.![](attachments/Pasted%20image%2020250611191021.png)
 - Use a **Query Field Type** when data needs to be referenced from a **data page** - e.g., a **case type** that manages flight instructions and creates flight plans might use a query to obtain the weather for an airport.

![](attachments/Pasted%20image%2020250611192542.png)

## Refresh Strategies for Data Pages

To prevent **stale** (out-of-date) data from causing issues, you have different **refresh strategies** to influence how Pega updates cached data used by **data pages**.
 - The challenge in designing a **data page refresh strategy** is balancing the chance that the **data page** has **stale** data against the performance impacts of refreshing.

The **load management** tab provides developers with three options for configuring the refresh strategy for read-only **data page** data:
 - **Reload once per interaction**
	 - Updates the **data page** each time the user accesses a page in memory
	 - Only available for pages in **thread** or **requestor** scope
 - **Do not reload when**
	 - Uses a *when* condition to test whether the data is considered **stale**
	 - If true, Pega considers the data current, and will not refresh
 - **Reload if older than**
	 - Uses a fixed interval of time to determine when the data is considered **stale**
	 - Careful consideration should be used to determine what timeframe is appropriate

![](attachments/Pasted%20image%2020250611194543.png)
 - Don't forget that data is only updated when the user requests it, no matter what refresh option is chosen

## Page Autopopulation

Pega can **autopopulate** page data, with the option to refer to or copy data that is stored in another system/app. There are two options:
 - **Refer to a Data Page**
	 - Use when you always need the **most current data**
 - **Copy data from a Data Page**
	 - Use when you need data from a **specific point in time**
	 - `When you copy data from a data page, the data is only refreshed when a data page paramater changes.`

## Data Access in UI Controls

`When you populate a list with data on a control, only the selected value is copied to the Data Model of a Case.`

## Simulated External Data Sources

Pega allows you to simulate external data sources - useful for situations when an external system is unavailable. As long as the data request and response formats are predictable, you can develop and test applications with these stubs until the application is ready to be connected to real data.
 - A good use for this is to test for the system's response using known data with a predictable outcome.

![](attachments/Pasted%20image%2020250611200616.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250611200727.png)
 - Useful for testing as well!

![](attachments/Pasted%20image%2020250611200821.png)

![](attachments/Pasted%20image%2020250611200916.png)
 - I kinda guessed the whole app needs the data, and that seems to be the right line of reasoning!

![](attachments/Pasted%20image%2020250611200950.png)
 - Remember that editable is saved to the *Data Page*, not back to the source

![](attachments/Pasted%20image%2020250611201249.png)
 - Read carefully. If you refer to a data page, it'll retrieve all data, and you definitely aren't populating.

![](attachments/Pasted%20image%2020250611202204.png)
 - Simulation populates a data View with test data if the **connector** for the data source is not yet configured, **Decision tables** are not used to simulate data from a data source.

![](attachments/Pasted%20image%2020250611202254.png)
 - Remember that **copied** data is from a certain time, and **referred** data is current.

![](attachments/Pasted%20image%2020250611202438.png)
 - Ditto above