## Unit Tests
Unit tests ensure that individual Pega rules are working together correctly
- Helps catch configuration errors early
- Prevents these errors from affecting broader case processing
- E.g. misrouted assignments

To run **unit tests**, you can use the "Run" option in Dev Studio to test Rules with sample data
 - Not all rules can be unit tested
	 - E.g. binary files
 - Pega rule resolution runs the highest version available
	 - E.g. if you run a test on a rule and there's a higher version of the rule, the higher version gets run
- After running a unit test, you can convert it into a **reusable unit test case** with expected results (assertions)
	- Much like automation testing!
	- Assertions include property value checks, decision results, expected run time, and page presence in memory
	- Multiple test cases can be **bundled together** into a test suite!

![](attachments/Pasted%20image%2020250622170257.png)

Best practices:
 - Write tests alongside Rule development
 - Prioritize automating tests that are run frequently
 - Try to create broad Rule coverage and modular tests
 - Use clear test names, document well!
 - Run tests regularly

![](attachments/Pasted%20image%2020250622170733.png)

## Creating Unit Test Cases

**Test Cases for Rules**
 - Unit tests can be converted into a reusable test case
 - After conversion, you can configure details like assertions, setup/cleanup actions, etc.
 - You can disable automatic execution if needed
	 - E.g. test suites or REST services
 - Test cases can include custom parameters
	 - *componentName* - Name of the component you're testing
	 - *pzRandomSeed* - Random seed for Split and Champion Challenger shapes

**Creating Unit Test Cases**
 - Create test cases by stepping through the process and inputting data for assignments and Decisions
	 - System records the data in a Data transform created after saving the test form
 - You can manually start recording and later refine the test input using *Edit Test Case*

## Test Coverage

![](attachments/Pasted%20image%2020250622173334.png)
 - *Industry best practices* are shown as an ideal test pyramid.
	 - Unit tests are the least expensive to run, are fast, and easy to maintain, and therefore make up the base
	 - Harder to run tests, such as functional and end-to-end testing are more expensive and take longer, and should represent fewer of the tests overall

**The Test Coverage Tool** measures which *Rules* in a Pega app are covered by automated tests
 - If it's 'uncovered', it's not being tested automatically
 - Two coverage report types can be generated:
	 - User-level test coverage report - shows coverage for rules tested by an individual user
	 - Application-level - aggregates results from multiple users, visible in the Application Quality dashboard
 - To start a coverage session, select the right application in Dev Studio -> Configure -> Application -> Quality -> Settings
	 - Note that multiple reports can be merged together as well!

![](attachments/Pasted%20image%2020250622173840.png)

---
## Quiz Notes

![](attachments/Pasted%20image%2020250622174005.png)
- Don't forget that while a transform is used to store recorded results, it's not what starts the test - this is the best answer

![](attachments/Pasted%20image%2020250622174155.png)
 - Don't overthink - review this

![](attachments/Pasted%20image%2020250622174333.png)

![](attachments/Pasted%20image%2020250622174440.png)