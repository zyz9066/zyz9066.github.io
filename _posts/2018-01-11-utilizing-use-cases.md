---
layout: post
title:  "Utilizing Use Cases"
date:   2018-01-11
tags:  [object oriented design]
---
# Use Cases
* **Title**: what is the goal?
* **Actor**: who desires it?
* **Scenario**: how is it accomplished?

### Use Cases: Title
Short phrase, active verb
* Register new member
* Transfer funds
* Purchase items
* Create new page
* Collect late payments
* Process accounts

### Use Cases: Actor
* User
* Customer
* Member
* Administrator
* ACMESystem

### Use Cases: Scenario as paragraph
**Title**: Purchase items\\
**Actor**: Customer\\
**Scenario**: Customer reviews items in shopping cart. Customer provides payment and shipping information. System validates payment information and responds with confirmation of order and provides order number that Customer can use to check on order status. System will send Customer a confirmation of order details and tracking number in an email.
### Use Cases: Scenario as steps
**Title**: Purchase items\\
**Actor**: Customer\\
**Scenario**:
1. Customer chooses to enter the checkout process
2. Customer is shown a confirmation page for their order, allowing them to change quantities, remove items, or cancel
3. Customer enters his/her shipping address
4. System validates the customer address
5. Customer selects a payment method
6. System validates the payment details
7. System creates an order number that can be used for tracking
8. System displays a confirmation screen to the Customer
9. Email is sent to the Customer with order details

### Use Cases: Scenario additional details
**Title**: Purchase items\\
**Actor**: Customer\\
**Secondary actor**: ...\\
**Scenario**: ...\\
**Description**: ...\\
**Scope**: ...\\
**Level**: ...\\
**Extensions**: Describe steps for out-of-stock situations\\
**Extensions**: Describe steps for order never finalized\\
**Precondition**: Customer has added at least one item ot shopping cart\\
**Postcondition**: ...\\
**Stakeholders**: ...\\
**Technology list**: ...\\
...

**Fully dressed use case templates**
# Identifying the actors
### Actors
Payroll Application: Payroll Administrator, Employee, Manager
* ---> ACMECorp Check Printing
* <---> HR System

### Identifying the actors
* External Systems / Organizations: External data sources, web services, other corporate apps, tax reporting, backup systems
* Roles / Security Groups: Visitor, member, administrator, owner
* Job Titles / Departments: Manager, Payroll Administrator, Production Staff, Executive Team, Accounting

Expense Approval System: Payroll Administrator, HR Staff, Janitorial, Part-Time Staff, Excutive Team, Production, Managers, Contractors, Marketing
* Requester: Primary actor
* Approver: Secondary actor

# Identifying the scenarios
Emphasize the goal of one encounter
* Purchase items
* Create new document
* Balance accounts

* Log in to application
* Write book
* Merge organizations

### Multiple Scenarios
**Title**: Purchase items\\
**Actor**: Customer\\
**Scenario**: Customer reviews items in shopping cart. Customer provides payment and shipping information. System validates payment information and responds with confirmation of order and provides order number that Customer can use to check on order status. System will send Customer a confirmation of order details and tracking number in an email.\\
**Extensions**: One or more items out of stock.
1. Customer removes out-of-stock item and continues
2. Customer cancels entire order
3. ...

**Extensions**: Customer payment method reject.
1. ...

**Active voice. Omit needless words.**
* **Not this**: The system is provided with the payment informationo and shipping information by the Customer.
* **This**: Customer provides payment and shipping information.
* **Not this**: The system connects to the external payment processor over HTTPS and uses JSON to submit the provided payment information to be validated, then waits for a delegated callback response.
* **This**: System validates payment information.

### Focus on Intention
**Title**: Purchase items\\
**Actor**: Customer\\
**Scenario**:
1. Customer chooses to enter the checkout process
2. Customer is shown a confirmation page for their order, allowing them to change quantities, remove items, or cancel
3. Customer enters his/her shipping address
4. System validates the customer address
5. Customer selects a payment method
6. System validates the payment details
7. System creates an order number that can be used for tracking
8. System displays a confirmation screen to the Customer
9. Email is sent to the Customer with order details

### Use Case prompts
* Who performs system administration tasks?
* Who manages users and security?
* What happens if the system fails?
* Is anyone looking at performance metrics or logs?

# Diagramming use cases
Knowledge Base: Search Articles, View Article, Manage Users, Create Article, View Analytics
* Visitor: Search Articles, View Article
* Contributor: Create Article
* Administrator: Manage Users, View Analytics

![]({{site.baseurl}}/images/object oriented design/use case.jpg)

|<<actor>><br>Analytics System|

View Article, View Analytics
# Employing user stories
### User Story
* **As a** (type of user)
* **I want** (goal)
* **so that** (reason)

* **As a** Bank Customer
* **I want** to change my PIN online
* **so that** I don't have to go into a branch

* **As a** User
* **I want** to search by keyword
* **so that** I can find and read relevant articles

* **As a** User
* **I want** to sort entries by date
* **so that** I can find the most recent content

* **As a** Reader
* **I want** to change the font and color scheme
* **so that** I can read in different lighting

* **As a** User
* **I want** to be prompted to save
* **so that** I don't lose any work

### User Stories and Use Cases

|User Stories|Use Cases|
|:-:|:-:|
|short - one index card|long - document|
|one goal, no details|multiple goals and details|
|informal|casual to (very) formal|
|"placeholder for conversation"|"record of conversation"|