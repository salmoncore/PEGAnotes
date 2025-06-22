## Localization

**Localization** ensures that Pega apps are tailored for users in different regions or languages.
 - Text may be translated into different languages
 - **Locale**-specific formats are used (e.g. date, currency)
	 - The user's **Locale** is determined by browser settings, or overridden by an **operator profile**.

**Language packs** contain pre-translated field values for Portals, and are imported into the app.
 - Apps can also use GenAI for external translation

**Localization process**:
1. Export text as a package (JSON or Excel)
2. Translate the package (either by a human or AI)
3. Import the translated package back into Pega
4. Use the **Localization landing page** in App Studio to manage packages

To **verify localization**:
1. Set your **operator locale** in Dev Studio to test localized interfaces
2. Log out/in to apply changes
3. Re-import updated packs if any text elements are still untranslated

Note that some elements **cannot be localized**:
 - Decision tables/trees
 - Case statuses
 - Radio/drop-downs in tables

![](attachments/Pasted%20image%2020250621171649.png)

## Design Considerations for Localization

App Studio has a **Localization landing page** to automate creating language-specific versions of an app, which can update text such as:
 - Labels
 - Tooltips
 - Captions
 - Instructions that appear in Views/Portals/etc.

**Caveats**:
 - Properties like **picklists** aren't automatically included in translation packages.
	 - Manually editing the localization file in Dev Studio is required.
 - Text containing **dynamic values** (e.g. welcoming messages using a username) should be localized by modifying the `pyMessages` rule.
 - Reusable content (like instructions or privacy notices) is handled through **paragraph rules**.
	 - Require manual translation, typically by editing the HTML in the translation package and uploading it back in.
 - Text in controls like dropdowns or radio buttons that source from **data pages** aren't included by default in translation packages.
	 - Requires manual population in the "Additional text" tab in App Studio

![](attachments/Pasted%20image%2020250621172638.png)

---

## Quiz Notes

![](attachments/Pasted%20image%2020250621172757.png)
 - Don't forget that the system both doesn't generate translations for properties with multiple values (e.g. picklists), and that locale, currency, and time zones aren't set on the **localization landing page**.

![](attachments/Pasted%20image%2020250621172949.png)
 - Don't overthink it

![](attachments/Pasted%20image%2020250621173250.png)
 - Remember that **hard-coding translated properties isn't an aspect of localization**.