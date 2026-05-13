# 1. What is Flow Builder?

Flow Builder is a Salesforce automation tool used to create business processes without writing code. It allows admins and developers to automate tasks, collect user input, update records, send emails, and guide users through screens using a drag-and-drop interface.

Flow Builder helps organizations reduce manual work, improve efficiency, and maintain accurate data in the system.

## Features of Flow Builder

- No-code/low-code automation
- Drag-and-drop interface
- Automates repetitive business tasks
- Works with records, emails, approvals, and notifications
- Supports user interaction through screens

---

# 2. Types of Flows

## Screen Flow

### Definition
A Screen Flow is an interactive flow that collects input from users through screens and performs actions based on the entered information.

### Characteristics
- Requires user interaction
- Displays forms and screens
- Used for guided processes
- Can create, update, or display records

### Example
A **College Admission Form** where students enter:
- Name
- Email
- Course Selection
- Phone Number

After submission, Salesforce automatically creates a student record.

### Use Case
Used when users need to enter or review information manually.

---

## Record-Triggered Flow

### Definition
A Record-Triggered Flow runs automatically when a record is created, updated, or deleted.

### Characteristics
- Fully automated
- Runs in the background
- No user interaction required
- Helps automate business logic

### Example
When a new student admission record is created:
- Send a confirmation email automatically
- Update available course seats
- Notify the admin

### Use Case
Used for backend automation and automatic updates.

---

# 3. Automation Ideas (5 Examples)

| Automation Idea | Description |
|---|---|
| Student Admission Confirmation | Automatically send an email after admission approval |
| Course Seat Update | Reduce available seats when a student enrolls |
| Fee Payment Reminder | Send reminders for pending fee payments |
| Attendance Alert | Notify parents if attendance is below minimum percentage |
| Faculty Assignment Notification | Inform faculty when assigned to a new course |

---

# 4. Flow Diagram

## College Admission Automation Flow

```text
Start
   |
   v
Student Submits Admission Form
   |
   v
Create Student Record
   |
   v
Check Course Availability
   |
   +-----> If Seats Available
   |             |
   |             v
   |      Confirm Admission
   |             |
   |             v
   |      Send Confirmation Email
   |             |
   |             v
   |      Update Remaining Seats
   |
   +-----> If Seats Not Available
                 |
                 v
          Show "Seats Full" Message
                 |
                 v
                End
```

---

# 5. Manual vs Automated Process

| Manual Process | Automated Process |
|---|---|
| Requires human effort | Runs automatically |
| Time-consuming | Faster execution |
| Higher chance of errors | More accurate |
| Difficult to track | Easy monitoring and tracking |
| Repetitive work for employees | Saves employee time |

---

# 6. Reflection: Why Automation Matters in Enterprise Systems

Automation is important in enterprise systems because it improves efficiency, accuracy, and productivity. Manual processes often consume time and may lead to human errors, while automated systems perform tasks quickly and consistently.

In Salesforce, automation tools like Flow Builder help organizations streamline business operations such as admissions, approvals, notifications, and record updates.

Automation also improves customer experience by providing faster responses and reducing delays. Overall, enterprise automation helps businesses save time, reduce operational costs, and increase overall performance.
