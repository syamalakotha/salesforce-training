# Salesforce Data Modeling and Automation

## 1. Difference Between App, Object, Record, and Field

| Term | Definition | Example |
|------|-------------|---------|
| **App** | A collection of tools, objects, tabs, and features designed for a specific business process. | College Management App |
| **Object** | A database table used to store related information. | Student Object |
| **Record** | A single entry stored inside an object. | One student's details |
| **Field** | A single piece of information inside a record. | Student Name, Roll Number |

### Simple Understanding
- **App** = Complete system
- **Object** = Table
- **Record** = Row in the table
- **Field** = Column in the table

---

# 2. Standard vs Custom Objects

| Standard Objects | Custom Objects |
|------------------|----------------|
| Already provided by Salesforce | Created by users/admins |
| Used for common CRM processes | Used for specific business needs |
| Cannot be deleted | Can be customized or deleted |
| Examples: Account, Contact, Opportunity, Lead | Examples: Student, Course, Admission |

## Examples

### Standard Object
- **Contact**
  - Stores customer or person details.

### Custom Object
- **Student__c**
  - Stores student information in a college management system.

---

# 3. College Data Model

## App Name
**College Admission Management System**

## Objects Used

| Object Name | Purpose |
|-------------|---------|
| Student | Stores student information |
| Course | Stores course details |
| Faculty | Stores faculty information |
| Admission | Stores admission records |
| Fee Payment | Stores payment details |

---

## Relationships

| Parent Object | Child Object | Relationship |
|---------------|--------------|--------------|
| Student | Admission | One-to-Many |
| Course | Student | One-to-Many |
| Student | Fee Payment | One-to-Many |
| Faculty | Course | One-to-Many |

---

## College Data Model Diagram

```text
Course
   |
   | One Course can have many Students
   |
Student
   |
   | One Student can have many Admissions
   |
Admission
   |
   | One Student can have many Fee Payments
   |
Fee Payment

Faculty
   |
   | One Faculty teaches many Courses
   |
Course
```
---
# 4. Formula Fields 

## What is a Formula Field?

A Formula Field in Salesforce is a custom field that automatically calculates values using a formula. It updates automatically whenever related data changes. Formula fields help reduce manual calculations and improve data accuracy.

---

# Example 1: Full Name Formula Field

## Formula

```text
First_Name__c & " " & Last_Name__c
```

## Explanation

- `&` is used to combine text values.
- `First_Name__c` stores the student's first name.
- `Last_Name__c` stores the student's last name.
- Salesforce automatically combines both fields and displays the full name.

## Use Case

This formula is useful for displaying the student's complete name automatically.



---

# Example 2: Remaining Seats Formula Field

## Formula

```text
Total_Seats__c - Filled_Seats__c
```

## Explanation

- `Total_Seats__c` stores the total number of seats available.
- `Filled_Seats__c` stores the number of seats already occupied.
- Salesforce automatically calculates the remaining seats.




---

# Example 3: Percentage Formula Field

## Formula

```text
(Obtained_Marks__c / Total_Marks__c) * 100
```

## Explanation

- `Obtained_Marks__c` stores the marks obtained by the student.
- `Total_Marks__c` stores the total marks.
- The formula automatically calculates the percentage.
# 5. Validation Rules 

## What is a Validation Rule?

A Validation Rule in Salesforce ensures that users enter valid and accurate data. If the entered data does not meet the defined condition, Salesforce displays an error message and prevents the record from being saved.

Validation rules help maintain data quality and consistency in the system.

---

# Example 1: Contact ZIP Code Validation

## Formula

```text
AND(
NOT(ISBLANK(Account.Id)),
MailingPostalCode <> Account.ShippingPostalCode
)
```

## Explanation

- `NOT(ISBLANK(Account.Id))`
  - Checks whether the contact is linked to an account.

- `MailingPostalCode <> Account.ShippingPostalCode`
  - Compares the contact ZIP code with the account ZIP code.
  - The rule becomes true if both ZIP codes are different.

- `AND()`
  - Both conditions must be true for the validation rule to trigger.

## Error Message

```text
Contact ZIP code must match the Account ZIP code.
```

## Use Case

Ensures that contact address details match the associated account information.

---

# Example 2: Student Minimum Age Validation

## Formula

```text
Age__c < 17
```

## Explanation

- `Age__c` stores the student's age.
- If the age is less than 17, Salesforce prevents the record from being saved.

## Error Message

```text
Student must be at least 17 years old.
```

## Use Case

Used in college admission systems to allow only eligible students to register.

---

# Example 3: Percentage Cannot Exceed 100

## Formula

```text
Percentage__c > 100
```

## Explanation

- `Percentage__c` stores the calculated student percentage.
- If the percentage value exceeds 100, Salesforce displays an error.

## Error Message

```text
Percentage cannot be greater than 100.
```

## Use Case

Prevents invalid academic percentage values from being entered into the system.
# 6. Reflection: Why Structured Enterprise Data Matters

Structured enterprise data is important because it helps organizations store, manage, and analyze information in an organized way. In Salesforce, data is structured using objects, records, and fields, which makes information easy to access and maintain. Properly organized data improves reporting, automation, and business decision-making. It also helps different departments work together efficiently because everyone uses the same accurate data. Structured data reduces duplicate records, minimizes errors, and improves overall productivity. In systems like college management, structured data helps track students, courses, admissions, and payments effectively.

