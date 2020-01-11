---
layout: post
title:  "Object-Oriented Analysis and Design"
date:   2018-01-11
tags:  [object oriented design]
---
# Object-oriented analysis and design processes
1. Gather *Requirements*
2. *Describe* the app
3. *Identify* the main objects
4. Describe the *Interactions*
5. Create a *Class Diagram*

# Gathering requirements
### Creating Requirements
* Functional Requirements: what does it do?\\
Features / Capabilities
* Non-Functional Requirements: what else?\\
Help, Legal, Performance, Support, Security

### Functional Requirements Examples
* System must display the heart rate, temperature and blood pressure of a patient connected to the patient monitor.
* Application must allow user to search by customer's last name, telephone number or order number.
* Program must allow receipts to be generated via email.
* Application must allow user to create 140-character message.
* Application must continue to function without network connection.
* System must automatically produce monthly Comparative Analysis (using current month and year-to-date as compared to same month last year and year-to-date last year) report by: Product (units sold and dollars), Product Category, Customer, Department, Region.Report must be in PDF format and automatically emailed to everyone in administrators group on first day of month.

### Non-Functional Requirements Examples
* System must respond to searches within 2 seconds.
* Help desk available by telephone, Mon-Fri 8am-6pm.
* Comply with all relevant HIPAA regulations.
* Be available 99.99% of time during business hours.

### FURPS / FURPS+
* **Functional** requirements
* **Usability** requirements
* **Reliability** requirements
* **Performance** requirements
* **Supportability** requirements\\
+ **Design** requirements, **Implementation** requirements, **Interface** requirements, **Physical** requirements

# Introduction to the Unified Modeling Language (UML)

|BankAccount|
|-
|`accountNumber`<br>`balance`<br>`dateOpened`<br>`accountType`|
|`open()`<br>`close()`<br>`deposit()`<br>`withdraw()`|

|BankAccount|
|-
|`accountNumber`<br>`balance`|
|`deposit()`<br>`withdraw()`|

|SavingsAccount|
|-
|(has every thing from BankAccount)<br>`interestRate`|

|CheckingAccount|
|-
|(has every thing from BankAccount)<br>`lastCheckNum`|

|InvestmentAccount|
|-
|(has every thing from BankAccount)<br>`accountRep`<br>**`withdraw()`**|

overriding