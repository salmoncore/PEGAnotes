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

## Six UI principles for App Studio
*"Walk through this order as much as you can"*

1. **Add value fast**
	 - It's generally fast and easy to prototype and make changes in App Studio
2. **Reduce components**
	- App Studio components are modular - they can be reused, so you don't need to constantly make new components
3. **Contextualizing user needs**
	- When building in PEGA, always think about designing for the end user
	- There's some nuance for who the "user" is, but think of who's using the tool
4. **Use Defaults**
	- Reiterating on being able to reuse components - they can be customized
5. **Provide tools and terms**
	 - PEGA reuses a lot of terms?
6. **UX design**
	- Decide on how components should look, how the flow works, etc.

## Navigation

![](attachments/Pasted%20image%2020250521172809.png)

PEGA has a navigation bar on the right-hand side, where there's options for:
 - **Overview** - Provides a summary of the application
 - **Case types (Processes)** - Links to each of the case types/processes associated with the app
 - **Data** - What data the app is using
 - **Channels** - Where the users are working from

## Application Development in App Studio

![](attachments/Pasted%20image%2020250521173012.png)

Think of two stages - **Prepare** and **Build**

### Prepare
 - Start with **Mockups** of the system, which can be made almost entirely in App Studio
 - You can get started with Dev Studio if you have external data - but most of the work will be in App Studio

### Build 
*There's two different options:*

**Option 1 - Fusion Teams**
*A combination of system architects and citizen developers*

**Option 2 - Business and IT Teams**
*This'll be how we'll operate!*
- **IT Teams** - Aka the Software Architects - *20% App Studio, 80% Dev Studio*
- **Citizen Developers** - Aka the Business Team - *80% App Studio, 20% Dev Studio*

*Note that **App Studio is NOT a substitute for Dev Studio** and **Dev Studio is NOT a supped-up App Studio** - they have different, complimentary features that support one another*

## Application Development in App Studio
App Studio has a few other benefits:
 - There are watchers in App Studio and guard rails
	 - They give you warnings for bad practice
		 - Can suggest test cases
		 - **Basically built-in help features**

## PEGA's Center-Out Business Architecture
**App Studio UX**
A simpler layout

**Dev Studio UX**
Has more options for what you can do, allows for advanced configurations

### Top-down vs Bottom-up
**Top-down**
 - **Start development from the presentation layer**
 - Higher-level vision of the application.
 - Might end up having to implement logic multiple times if requirements change

**Bottom-up**
 - **Start development from the data access layer**
 - E.g. start by setting up data tables, making modular data elements, etc.
 - Becomes difficult handling data from multiple data sources

*There's tradeoff to each option.*

## Center-Out Approach
*PEGA has it's own approach which will attempt to fix the downsides of these two approaches.*

"Instead of starting at the top or bottom, we'll work in the middle - **Start with the Business Logic.**"
 - Manage intelligence centrally - bring the stakeholders as close to the process as possible
 - Focus on outcomes
 - Compartmentalizes the frontend and backend - you can swap data sources, for example, and it should be easy to do

