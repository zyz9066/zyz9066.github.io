---
layout: post
title:  "Database Modeling: Indexing and Optimization"
date:   2018-01-18
tags:  [databases]
---
# Understanding indexes
Clustered Index
```sql
Select * From Customer
Where CustomerID = 584;
```
Full-Table Scan
```sql
Select * From Customer
Where LastName = 'Smith';
```
Non-Clustered Index on LastName

|LastName|CustomerID|
|:-:|:-:|
|Allen|592|
|Bailey|432|
|Blackwell|584|
|...|...|
|...|...|
|...|...|
|Smith|551|
|...|...|

### Indexing
* Indexing is not just "upfront" work
* Indexing is a trade-off.
Faster reads and slower writes
* Indexing can be tweaked without breaking applications.

# Understanding write conflicts
### Conflicts and Isolation
The ACID Test
* Atomic
* Consistent
* Isolated
* Durable

Alice
```
BEGIN TRANSACTION
  get balance of Joint account ($10000)
  get balance of Alice account ($50)
  update balance of Joint account ($10000 - $1000)
  update balance of Alice account ($50 + $1000)
COMMIT
```
Bob
```
BEGIN TRANSACTION
  get balance of Joint account  ($10000)
  get balance of Alice account  ($45)
  update balance of Joint account ($10000 - $1000)
  update balance of Alice account ($45 + $1000)
COMMIT
```
### Pessimistic Locking
Alice
```
BEGIN TRANSACTION
  get balance of Joint account  ($10000)
  get balance of Alice account  ($50)
  update balance of Joint account ($10000 - $1000)
  update balance of Alice account ($50 + $1000)
COMMIT
```
Bob
```
BEGIN TRANSACTION
  get balance of Joint account  REFUSED
  get balance of Joint account  ($9000)
  get balance of Alice account  ($45)
  update balance of Joint account ($9000 - $1000)
  update balance of Alice account ($45 + $1000)
COMMIT
```
### Optimistic Locking
Alice
```
BEGIN TRANSACTION
  get balance of Joint account  ($10000)
  get balance of Alice account  ($50)
  update balance of Joint account ($10000 - $1000)
  update balance of Alice account ($50 + $1000)
COMMIT
```
Bob
```
BEGIN TRANSACTION
  get balance of Joint account  ($10000)
  get balance of Alice account  ($45)
  update balance of Joint account ($10000 - $1000)
  error - dirty read detected - rollback
```
# Stored Procedures and Injection Attacks
### Stored Procedures
```sql
CREATE PROCEDURE HighlyPaid()
  SELECT * FROM Employee
  WHERE Salary > 50000
  ORDER BY LastName, FirstName
END;

CALL HighlyPaid();
```
Stored Procedures Can Have Parameters
```sql
CREATE PROCEDURE EmployeeInDept(IN dept VARCHAR(50))
  SELECT * FROM Employee
  WHERE Department = dept
  ORDER BY LastName, FirstName
END;

CALL EmployeeInDept('Accounting');
```
### SQL Injection
```java
sqlString = "SELECT * FROM Orders WHERE CustomerID = '" + textbox.value + "';";
sqlString = "SELECT * FROM Orders WHERE CustomerID = 'ABC551';";
executeSQL(sqlString);
```
<ul>`x'; SELECT * FROM Users; --`</ul>
```java
sqlString = "SELECT * FROM Orders WHERE CustomerID = 'x'; SELECT * FROM Users; --'";
executeSQL(sqlString);
```
```sql
SELECT * FROM Orders WHERE CustomerID = 'x';
SELECT * FROM Users;
--'
```
<ul>`x'; DROP TABLE Orders; --`</ul>
```java
sqlString = "SELECT * FROM Orders WHERE CustomerID = 'x'; DROP TABLE Orders; --'";
executeSQL(sqlString);
```
```sql
SELECT * FROM Orders WHERE CustomerID = 'x';
DROP TABLE Orders;
--'
```
