## Passed Deadline Interval

The **Passed Deadline Interval** defines when to take action due to a step that's beyond the deadline.
 - Interval measures the *time passed since the deadline*
 - You configure the passed deadline interval on the **Service-Level Agreement (SLA) Rule** in **Dev Studio**
	 - SLAs can be created in **App Studio**, but full configuration occurs in Dev Studio

![](attachments/Pasted%20image%2020250619165227.png)

Unlike goals and deadlines, **passed deadline intervals** can:
 - Repeat a fixed number of times, or continue until the assignment is complete
 - Increase assignment **urgency**, and trigger escalation **actions** each time the interval elapses

**Urgency Cap:**
- The max urgency is **100**
	- If urgency is already at 100, Pega still executes other escalation actions like notifications, even if urgency doesn't increase further
- E.g., for a timesheet submission, a company sets a passed deadline interval of **24 hours**, that then repeats 10 times
	- Each time the interval elapses, a reminder is sent until the timesheet is submitted

```
The initial Urgency on the Case Type is set to 10. An Assignment Service-Level Agreement is configured with the following details:

- Goal: 12 hours and increase Urgency by 20

- Deadline: 24 hours, increase Urgency by 30, and then send an email Notification to the assignee

- Passed deadline: 6 hours, increase Urgency by 40, send an email Notification to the assignee and manager, and limit events to 3

Which three statements are true 37 hours after the Case reaches the Assignment? (Choose Three)
```
 - Urgency starts at 10. Increase by 20 at 12 hours. After 24 hours, increase by 30 and send an email. Past deadline, every 6 hours increase urgency by 40, send an email to assignee and manager - *only do this 3 times*.
 - At 37 hours...
	 - 10 -> 30 (+20 at 12 hours, 37-12 = 25hrs remaining)
	 - 30 -> 60 + email sent to assignee (25-12=13 hrs remaining)
	 - 60 -> 100 + email to assignee and manager (13-6=7hrs)
	 - 100 -> 100 + email to assignee and manager (7-6=1hrs)
 - In total:
	 - 100 urgency
	 - 3 emails to assignee
	 - 2 emails to manager

![](attachments/Pasted%20image%2020250619170439.png)

---

## Quiz Notes

```
An Assignment is configured with the Service-Level Agreement described in the following list. Passed deadline intervals can repeat. 

• **Initial Urgency**: 5

• **Goal**: 12 hours and increase Urgency by 10

• **Deadline**: 24 hours and increase Urgency by 15

• **Passed deadline**: 4 hours, increase Urgency by 20, and limit events to 5

What is the Assignment Urgency 36 hours after the Case reaches the Assignment?
```
 - 5 urgency, 36 hours to go
 - 5 -> 15, 24 hrs left
 - 15 -> 30, 12 hrs left
 - 30 -> 50, 8 hrs left
 - 50 -> 70, 4 hrs left
 - 70 -> 90, 0 hrs left
![](attachments/Pasted%20image%2020250619171355.png)

```
A customer service representative (CSR) must respond to emails within 24 hours. Otherwise, the Assignment is considered late, and the Urgency increases by 20. For every additional 6 hours that the CSR does not respond, the CSR's manager is notified, and the Urgency increases by 20. If the Case reaches the Assignment at 4 P.M. Tuesday and the Assignment starts with an Urgency of 10, what is the Assignment Urgency at 1 P.M. Thursday?
```
 - 4pm Tuesday -> 1pm Thursday
	 - 8hrs Tuesday
	 - 24hrs Wednesday
	 - 13hrs Thursday
	 - = 45 hours
 - 10 -> 30, 21 hrs / 6 = 3.5, 3 passed deadline intervals elapse
 - 30 -> 50 -> 70 -> 90
![](attachments/Pasted%20image%2020250619172827.png)

![](attachments/Pasted%20image%2020250619172902.png)
