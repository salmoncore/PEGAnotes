## Mobile App Channels
 - App Studio can be used to configure **mobile Channels** - essentially, mobile app versions of your Pega application
	 - Constellation UI will even use native Android and iOS components!

![](attachments/Pasted%20image%2020250620211703.png)
 **Mobile Channel** has tabs for configuring:
 - **Content** - controls the content available to users in the mobile app
	 - E.g. customizing app navigation, adding or removing app pages, setting up swipe actions, etc.
- **Configuration** - controls basic app functionality
	- E.g. setting the app name, app user authentication settings, etc.
- **Layout** - controls app branding and styling
	- E.g. setting UI element colors, app icon, etc.
- **Manage** - controls administrative functions
	- E.g. log access and administrative push notifications

**Mobile App Content**
 - *List Pages* - Display data with built-in transitions and search functionality
 - *Case Pages* - View and edit **Cases** with customizable views and widgets like to-do lists or Pulse (Posts sent to users)

**Mobile App Security**
 - A single user Persona determines who has access to the **Channel**
 - Configure app locking with biometrics or passcode here as well

**Branding**
You can configure the app's splash screen and app icon

**Mobile App Preview**
 - You can load a preview version of the app to test content and perform testing before generating native packages
 - Some features (e.g. push notifications) are limited in preview mode

**App Distribution**
 - Requires HTTPS access, certificate setup, and a mobile build server configuration to generate Android/iOS installation packages

![](attachments/Pasted%20image%2020250620213220.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250620213320.png)
 - Straightforward, just remember that each **mobile channel** requires it's *own **persona***

![](attachments/Pasted%20image%2020250620213419.png)
 - Study this, it's not super intuitive lol

![](attachments/Pasted%20image%2020250620213450.png)
