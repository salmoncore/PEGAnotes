***Video 1 Content***

*When you're using PEGA, it can help you automate website development - but doesn't limit using custom front/backends.*

![](attachments/Pasted%20image%2020250521124835.png)

We're training to become **system architects** - how does this compare to citizen developers?
 - **Citizen Developers** are closer to the business logic, but still familiar with low-code
 - **System Architects** have the technical know-how, can implement custom features

Keep in mind the thought of the **business outcomes** - we'll come back to this.

## Low Code Development

![](attachments/Pasted%20image%2020250521125709.png)

By **visual**, typically we mean that there's a GUI with drag-and-drop elements that can be used instead of having to manually develop the entire UI.

To be clear, there *is* still code - it's just been abstracted away. In PEGA, the foundation is written in Java. (*Note that we're not gonna be looking at the Java - it's all proprietary.*)

---
### Terminology
In PEGA, our processes are called **cases**, or **case types**.

![](attachments/Pasted%20image%2020250521134409.png)

Let's say we wanted to develop an interface for a job application. A new applicant will take in some information, there's a recruiter review, etc. 
 - PEGA has GUI options to allow **citizen developers** to build out the logic of the app, making implementing business logic easy - note how all of this flow so far doesn't require any coding. 
 - It still allows for **system architects** to build out custom functionality, without having to worry about the business logic that's handled by subject matter experts.

---

## Benefits of Low Code
 - Since you can reuse elements with a GUI, it's **faster** to develop
 - There's shortened feedback loops for prototyping, you can experiment quickly 
 - Having stakeholders with business-side knowledge participating makes development more collaborative

## Building with Low Code
 - Traditionally, when developing a cross-platform app, you'll have to develop a version of the app to cater to each platform
 - With low-code and reusable elements, you have a much simpler means of laying out the content and building an application with the same elements from both platforms
 - **A channel is where a user goes to interact with your application** - the *platform*
	 - A mobile app
	 - A web browser
	 - A chatbot
	 - etc...

 **PEGA allows you to connect to other APIs, your own systems, and etc.**
 ![](attachments/Pasted%20image%2020250521140423.png)

It does this while remaining low-code - *which might get a little tedious.*

## Low Code and Developers

So, you have *non-developers* who can now help to implement business logic...
And *developers* can use GUI tools to build advanced functionality faster...

To keep everything organized, there's PEGA ***Workspaces/Studios*** (we'll see more soon).

***Patterns*** are reusable components that can be customized for PEGA, of which *developers can make a whole suite of.*

## PEGA Platform Workspaces/Studios
*Either name is valid, apparently.*

There's four main studios:

 - **App Studio**
	 - **Provides core development features, fast development time**
	 - Allows non-devs to build out cases, business logic, etc.
	 - Typically, you start with low-code, building out frameworks and components
	 - Eventually, you can move to something more advanced, like...
 - **Dev Studio**
	 - Still technically a low-code environment
	 - There *are* places where you can add your own code
	 - More technical and developer-oriented
 - **Prediction Studio**
	 - Customized for data analysis, AI
 - **Admin Studio**
	 - For IT staff, management
	 - Where DevOps will happen

We'll primarily use App Studio, but may check in on Dev Studio

## Taking a look at PEGA

![](attachments/Pasted%20image%2020250521143917.png)

Here's the place you typically land in PEGA studio.

*There's a lot of navigating here.*

---

### Even More Terminology

![](attachments/Pasted%20image%2020250521144735.png)

Each of these columns represent a ***stage*** in the process. We're starting with the *Create* stage, and we move to the right.

---

## Making a new Application

When you select *Build from Scratch*, you'll then be asked: *Choose your UI architecture*

 - **Constellation**
	 - What we'll be primarily using
 - **Traditional UI**
	 - Older interface - may have the same functionality

***When going through the modules, pay attention to what UI you're using.***
Functionality won't change, but the *implementation* might.
### Application Layers

![](attachments/Pasted%20image%2020250521150211.png)

 - **Rules Layer** *(Middle)*
	 - `From layer: Theme-Cosmos`
		 - This comes from the **OOTBC** - `Out-Of-The-Box-Components`
 - **Base Layer** *(Bottom)*

---
### Data Objects

![](attachments/Pasted%20image%2020250521152207.png)

*We'll get more into this later - there's some nuance to what's going on here. It's not exactly like a database, PEGA has it's own system for linking data to identifiers.*

---

***Video 2 Content***

