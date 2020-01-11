---
layout: post
title:  "Database Modeling: Relationships"
date:   2018-01-16
tags:  [databases]
---
# Creating Relationships
### Entity Relationship Diagram

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

### Relationship (Cardinality) Options
<small>One-to-One</small>  
**<big>One-to-Many</big>**  
Many-to-Many
### The Natural Order of Database Design

|Customer|
|:-:|
|CustomerID (PK)|

<small>places</small>

|Order|
|:-:|
|OrderID (PK)|

# Defining One-to-Many Relationships
One Customer ---> Many Order (1, $$\infty$$)  
Primary Key (PK)  
Foreign Key (FK)

|Order|
|:-:|
|OrderID (PK)<br>CustomerID (FK)|

# Exploring One-to-One Relationships
Employee - DriversLicense  
Customer - OrderItem - Product
# Exploring Many-to-Many Relationships
Author - Book  
Class - Student: ClassStudent
# Relationship rules and referential integrity
Referential Integrity  
* Cascading Delete  
* Cascading Nullify
* No Action
