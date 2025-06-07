## Controls and Presentation

**User interface elements in Pega**
 - Pega comes with some basic input controls that are available out of the box:
	 - Autocomplete controls
	 - Check Boxes
	 - Drop-down lists
	 - etc
 - You can use **themes** to configure the styling of UI elements

![](attachments/Pasted%20image%2020250607120350.png)

This is the **default** theme, Pegasus

![](attachments/Pasted%20image%2020250607120424.png)

## Dynamic Functionality on UI Elements

**Dynamic UI design** is the practice of *designing elements on a UI to adapt according to user input*.
 - You can show, hide, or disable UI elements programmatically.
 - E.g., a loan might ask for your spouse's information ***if*** you're married - otherwise, those fields may be hidden.

**Dynamic Attributes for UI Elements include:**
 - **Always** - the UI element always appears
 - **Custom condition** - the UI element appears when an expression returns true
	 - *Note that rules can be used for the expression as well*
 - **When Rule** - the UI element appears when a **Rule** returns true
 - **If not blank** - the UI element appears when the value of a field is not blank
 - **If not zero** - the UI element appears when the value of the field is not zero

**Disabled Settings for UI elements include:**
 - **Never** - the UI element will never be disabled
 - **Always** - the UI element will always be disabled
	 - Can be used to show information that the user can't modify
 - **Custom condition** - the UI element is disabled when an expression returns true
	 - *Note that rules can be used for the expression as well*
 - **When rule** - the UI element is disabled when a **Rule** returns true

**Required Field settings for UI elements include:**
 - **Never** - the field is never required to be filled out
 - **Always** - the field is always required to be filled out
 - **Custom condition** - the field is required to be filled out when an expression returns true
 - **When rule** - the field is required to be filled out when a **Rule** returns true

![](attachments/Pasted%20image%2020250607121352.png)
^ I guess the checkbox can't be evaluated as blank or not?

---

## Quiz Notes

![](attachments/Pasted%20image%2020250607121512.png)

![](attachments/Pasted%20image%2020250607121552.png)

![](attachments/Pasted%20image%2020250607121655.png)