**Building Accessible Applications**

Constellation components are built to be accessible out-of-the-box, but **authors must still apply best practices**.
 - Inclusive design emphasizes the proper use of **headings**, **regions**, and **navigation tools** to aid all users (especially those with assistive technologies)
 - Labels allow users to better understand interactive content on a page (e.g. "First Name" describing a text field's purpose)
	 - Labels come preconfigured, but can be customized
 - Additional context tools, e.g. **tooltips**, **placeholders**, and **helper text** improves clarity
	 - **Tooltips** - Generally used for icon buttons, functionally replaces the title
	 - **Placeholder text** - provides guidance on form field inputs, e.g. "Enter vehicle color"
	 - **Helper text** - provides inline visible text for a selected component
	 - **Help icon** - provides more in-depth guidance

**Tables** support:
 - **Instructions** - allows screen readers to identify how to navigate the table
 - **Captions** - identifies table content for screen readers
 - **Single menu action** - enables keyboard navigation
 - **Links** - Navigating to a cell via a link focuses that cell
 - **Bulk actions** - checkboxes and radio buttons are accessible within the table, can be used in a bulk action
 - **Progressive data loading** - allows data to be retrieved dynamically, works with screen readers
 - **Editing** - if editing the table is required, it's recommended to configure a modal triggered by a button or an icon

**Error validation** is done via client and server-side validation - if an error is detected in either side, the user is notified by a visual indication, announcement to a screen reader, and focus management for keyboard users.

![](attachments/Pasted%20image%2020250621195159.png)

## Accessibility Testing Methods in Constellation

There's three testing methodologies, each with their own benefits and drawbacks:
 - **Automated Accessibility Testing**
	 - Quick and commonly used
	 - Tools scan the DOM and flag issues like missing labels, non-descriptive links
	 - Examples: axe DevTools, WAVE, SiteImprove, ANDI
	 - Covers ~30% of WCAG compliance needs
		 - Use automated testing in conjunction with another option
 - **Manually Testing with Assistive Technology**
	 - Compliments automation by addressing gaps
	 - Involves using tools like:
		 - Screen readers
		 - Voice recognition
		 - Magnifiers
	 - Benefits:
		 - Simulates user experiences
		 - Validates code behavior that users and their tech relies on
 - **Testing with Real Users**
	 - Most authentic feedback comes from users with disabilities
	 - Users demonstrate how they interact with assistive tech
		 - Screen readers
		 - Shortcut keys
		 - Keyboard shortcuts
		 - Magnification via system tools
	 - Provides insight into usability, builds empathy, inspires improvements

![](attachments/Pasted%20image%2020250621195918.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250621195957.png)
 - Easy

![](attachments/Pasted%20image%2020250621200024.png)
 - ...Also easy by process of elimination

![](attachments/Pasted%20image%2020250621200051.png)
- omg

![](attachments/Pasted%20image%2020250621200426.png)
 - Study, remember that field labels use the field name and are visible by default, as well as the fact that captions are for identifying table content for screen readers