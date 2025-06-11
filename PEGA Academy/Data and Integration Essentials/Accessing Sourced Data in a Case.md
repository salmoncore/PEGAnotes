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

