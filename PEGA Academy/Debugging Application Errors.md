## The Tracer
 - It's a debugging tool in Pega, used to **trace events during application runtime**
	 - Helps identify the root cause of errors in case processing
	 - E.g., can be used to troubleshoot unexpected behavior from declare expressions or issues in drop-down lists that are populated by data pages

![](attachments/Pasted%20image%2020250622143420.png)
 - Accessed from this button

**Tracer Events**
 - Logs events in chronological order with color-coding:
	 - Gray - Activity processing
	 - Orange - Flow, decision, declarative rule event
	 - Light blue - Database/cache operation

![](attachments/Pasted%20image%2020250622144223.png)

![](attachments/Pasted%20image%2020250622144303.png)

**Error Identification**
 - Shows status per event (`GOOD`, `FAIL`)
 - Helps track the chain of events to pinpoint root causes, not just the final failure

![](attachments/Pasted%20image%2020250622144704.png)

The **Clipboard Tool** is what allows you to inspect data pages, properties, and current values in memory during case execution.
 - Works only in **preview mode**, not in the live, end-user portal
 - Pega **Constellation** considerations:
	 - Clipboard tool is limited due to the stateless architecture
	 - Tracer shows interactions organized by *request ID*, accounting for multiple simultaneous requests
 - Note that the **performance tool** should be used to assess application performance, e.g. slow execution

![](attachments/Pasted%20image%2020250622150632.png)

## Tracer Settings Management

The **tracer tool** is resource-heavy - it's best to configure it to capture **only what you need** in order to reduce the performance hit.
 - The **trace toolbar** includes controls like:
	 - Pause - Suspend event logging
	 - Clear - Removes logged events from the screen
	 - Save - Generates an XML file listing the events on the screen
	 - Settings - Has **event filters** for tuning which events, event types and Rulesets to trace
		 - Selecting **break conditions** stops the tracer when the system generates an error
		 - Filtering helps limit what's captured, e.g. local variables
 - **Only one tracer is allowed per operator, per node**

**Breakpoints** are used to pause tracing when specific activities occur
 - Helpful for identifying the moment something happens
 - Trace resumes after you hit play or after an hour elapses, whichever comes first

The **Watch function** is similar to breakpoints, but **watch** monitors a *specific property value* to determine if and when it changes
 - Changes are highlighted, property inspector shows old and new values for analysis
![](attachments/Pasted%20image%2020250622154653.png)

![](attachments/Pasted%20image%2020250622154711.png)

## Developer Tools for Examining Applications

You can use Dev Studio to access and inspect View rule metadata
- Search for `ViewName pxObjClass: Rule-UI-View` to find the list of available views in the app
- Enabling `pxEnableC11nDev` lets you to view associated JSON

**Browser development tools** can still be used within Pega
*Note that these examples are taken from Chrome:*
 - Inspect scripts in the **console tab**
 - Track DX API calls in the **network tab**
 - Access local/session storage in the **application tab**

**DevTools**
 - **React DevTools** (plugin) can let you view component hierarchies
	 - You can use `$r.props.getPConnect()` for runtime metadata
 - **Redux Devtools** (also a plugin) helps you monitor state changes, actions, and step through state changes to pinpoint issues related to incorrect updates
 - The **Xray tool** can overlay UI element metadata on the screen
	 -  Activate with `PCore.getDebugger().toggleXRay(true)`
	 - Requires running from Dev Studio
- **DebugPegaAPI**, when set to true, logs detailed DX API request/response information, including input data, errors, and exception metadata
- **Client-Side Data Pages** - run `PCore.getDataPageUtils();` in the browser console to view cached Data Pages stored outside redux

![](attachments/Pasted%20image%2020250622162620.png)

---
## Quiz Notes

![](attachments/Pasted%20image%2020250622163257.png)

![](attachments/Pasted%20image%2020250622163315.png)

![](attachments/Pasted%20image%2020250622163348.png)

![](attachments/Pasted%20image%2020250622163444.png)

![](attachments/Pasted%20image%2020250622163455.png)