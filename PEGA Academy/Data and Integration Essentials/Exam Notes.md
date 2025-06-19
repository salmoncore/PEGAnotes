![](attachments/Pasted%20image%2020250619142219.png)
  - Study. Remember that *Application* isn't a valid scope and that *Request* and *Thread* creates a data page for each requestor/case, respectively. 

![](attachments/Pasted%20image%2020250619142638.png)
 - Study. Remember that *Validate Patterns* can't be used to test a pattern - you need an *edit Validate Rule* to check the formatting.

![](attachments/Pasted%20image%2020250619143047.png)
 - Study, review [Accessing Sourced Data in a Case](Accessing%20Sourced%20Data%20in%20a%20Case.md) - If you refer to a data page, it'll retrieve all data, and you definitely aren't populating.

![](attachments/Pasted%20image%2020250619143222.png)
 - Study, review [Application Data Manipulation](../Low-Code%20App%20Builder%20Extended/Application%20Data%20Manipulation.md) 

![](attachments/Pasted%20image%2020250619143532.png)
 - **Study**, review [Validating Data in Dev Studio](Validating%20Data%20in%20Dev%20Studio.md) - all others can be done via App Studio, but user input validation needs to be done within Dev Studio!

![](attachments/Pasted%20image%2020250619143752.png)
 - Straightforward enough

![](attachments/Pasted%20image%2020250619143835.png)
 - Straightforward, but review the explanation in [Validating Data in Dev Studio](Validating%20Data%20in%20Dev%20Studio.md) - `Read carefully - we're looking for the option that prevents the user from *entering* an invalid combination. A Decision Rule or Validate/Edit Validate Rule might work, but it'd have to be assessed after the user already entered their information.`

![](attachments/Pasted%20image%2020250619144324.png)
 - Note that a **Work Group** would be used to designate a default **work queue** for a team, and that **decision logic** would be used to suggest a product based on search history.

![](attachments/Pasted%20image%2020250619144617.png)
 - Study. Configuration settings use role-based access control, so you don't need to know the name.

![](attachments/Pasted%20image%2020250619144951.png)
 - Straightforward enough, just remember that reloads occur when the data is accessed, not just as soon as it's set to reload.

![](attachments/Pasted%20image%2020250619145401.png)
 - **Study.** Refer to [Creating and Setting Application Variables](Creating%20and%20Setting%20Application%20Variables.md) - You don't need configuration settings to change the values of an element of a list, and you can only group related business functions from one app.

![](attachments/Pasted%20image%2020250619145657.png)
 - Study. Note that the *Save Data Page Step* saves the data page you reference on the step, **not** all data pages. Also, using *Save Data Pages* **does** save memory when you have multiple requests for the same data that can now be reached from one place.

![](attachments/Pasted%20image%2020250619145728.png)
 - Straightforward, just remember that **Data Transforms** are good for copying data between pages.

![](attachments/Pasted%20image%2020250619150447.png)
 - **Study** - note that without selecting the *Call superclass Data Transform* option, the parent values can't be used.

![](attachments/Pasted%20image%2020250619150620.png)
 - Straightforward - just remember that referring to data tends to have a higher risk of overwriting than copying.

![](attachments/Pasted%20image%2020250619151048.png)
 - Straightforward, remember that you can't configure data transforms to filter on a view. Option 4 is apparently dangerous for data integrity, so maybe study that?

![](attachments/Pasted%20image%2020250619151308.png)
 - Straightforward

![](attachments/Pasted%20image%2020250619151353.png)
 - Straightforward, remember - *the Database save option is only for data pages with a page structure*, e.g. not a page *list* structure.

![](attachments/Pasted%20image%2020250619151702.png)
 - Straightforward - remember again that copying data allows you to pull the data values from a certain time.

![](attachments/Pasted%20image%2020250619151756.png)
 - Straightforward again, remember that referring to data is the most up-to-date option.