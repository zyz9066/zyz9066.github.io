---
layout: post
title:  "Database Modeling: Tables"
date:   2018-01-15
tags:  [databases]
---
<!-- Introduction to database modeling -->
# Planning your database
### What's the Point?
"It's a database to store product and order information."  
or...  
"We help customers find books, discover what others thought about them, purchase and track their orders, contribute their own reviews and opinions, and learn about other products they might like based on people with similar reading habits."
### What Do You Have Already?
* Physical items
Forms, order sheets, printouts, and handouts
* People and expertise
* An existing "database"
Spreadsheets and text files

### Entities

|Customer|

<small>places</small>

|Order|

<small>contains</small>

|Order Item|

<small>refers to</small>

|Product|

---

|Comment|

*<small>on</small>*

|Blog Post|

*<small>belongs to</small>*

|Author|

---

|Paycheck|

<small>for</small>

|Employee|

<small>is in</small>

|Department|

# Identifying columns and selecting data types
### Entities and Attributes

|entity|Customer|
|attributes|name<br>email<br>address<br>phone|

### Employee
* FirstName ( or first_name, firstname, fName, strFirstName, firstName, etc. )
* LastName
* DateHired
* SalaryGrade
* AddressLine1
* AddressLine2
* City
* State
* Zip
* Email
* Photo
* (etc.)

|FirstName|character|not NULL||
|LastName|character|not NULL||
|DateHired|date|not NULL|default: today|
|SalaryGrade|integer|not NULL||
|AddressLine1|character|not NULL||
|AddressLine2|character|NULL||
|City|character|not NULL||
|State|character(2)|not NULL||
|Zip|character|not NULL||
|Email|character|not NULL|pattern match:email|
|Photo|binary|NULL||
|(etc.)||||

[MySQL Data Types](https://dev.mysql.com/doc/refman/8.0/en/data-types.html)  
[SQL Server Data Types](https://docs.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-2017)
# Choosing primary keys
**Primary Key (PK)** (**natural** key)  
integer, auto-increment
<!-- Using composite keys -->
