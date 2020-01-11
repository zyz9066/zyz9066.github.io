---
layout: post
title:  "Database Modeling: Querying"
date:   2018-01-17
tags:  [databases]
---
# Creating SQL Queries
### SQL Keywords
* Select
* From
* Where
* Order by
* Group by
* Join
* Insert into
* Update
* Delete
* Having
* In

```sql
SELECT columns FROM table
WHERE condition;
SELECT FirstName, LastName FROM database.table
WHERE Salary > 50000;
SELECT * FROM HumanResources.Employee
WHERE LastName = 'Green';
```
# Structuring the **WHERE** clause
```sql
SELECT * FROM Employee
WHERE LastName = 'green';
SELECT * FROM Employee
WHERE EmployeeID = 474;
SELECT * FROM Employee
WHERE Department = 'Marketing' OR Department = 'Sales';
SELECT * FROM Employee
WHERE Department IN ('Marketing', 'Sales');
SELECT * FROM Employee
WHERE LastName LIKE 'Green%';
SELECT * FROM Employee
WHERE LastName LIKE 'Sm_th';
SELECT * FROM Employee
WHERE MiddleInitial IS NOT NULL;
```
String values in SQL are surrounded in **single quotes**  
\>, <, >=, <=, <> <small>not equal</small>
# Sorting Query Results
```sql
SELECT Description, ListPrice, Color FROM Product
ORDER BY ListPrice DESC;
SELECT * FROM Employee
WHERE Salary > 50000
ORDER BY LastName, FirstName;
```
# Using Aggregate Functions
```sql
SELECT COUNT(*) FROM Employee
WHERE Salary > 50000;
```

|results|
|:-:|
|132|

```sql
SELECT MAX(ListPrice) FROM Product;
SELECT MIN(ListPrice) FROM Product;
SELECT AVG(ListPrice) FROM Product;
```
```sql
SELECT SUM(TotalDue) FROM Order
WHERE CustomerID = 854;
```
```sql
SELECT COUNT(*), Color FROM Product
GROUP BY Color;
```
# Joining Tables
```sql
SELECT FirstName, LastName, HireDate, Employee.DepartmentID, Name, Location FROM Employee
INNER JOIN Department ON Employee.DepartmentID = Department.DepartmentID;
SELECT FirstName, LastName, HireDate, Employee.DepartmentID, Name, Location FROM Employee
LEFT OUTER JOIN Department ON Employee.DepartmentID = Department.DepartmentID;
SELECT FirstName, LastName, HireDate, Employee.DepartmentID, Name, Location FROM Employee
RIGHT OUTER JOIN Department ON Employee.DepartmentID = Department.DepartmentID;
```
# Inserting, updating, and deleting
**C**reate <small>Insert</small>  
**R**ead <small>Select</small>  
**U**pdate <small>Update</small>  
**D**elete <small>Delete</small>

```sql
INSERT INTO table (column1, column2...) VALUES (value1, value2...);
INSERT INTO Employee (FirstName, LastName, Department, Salary) VALUES ('Joe', 'Allen', 'Sales', 45000);
```
EmployeeID: auto  
HireDate: default value
Email: null
```sql
UPDATE table SET column = value
WHERE condition;
UPDATE Employee SET Email = 'joea@hplussport.net'
WHERE EmployeeID = 734;
```
```sql
DELETE FROM table
WHERE condition;
DELETE FROM Empolyee
WHERE EmployeeID = 734;
```
```sql
DELETE FROM Empolyee;
```
```sql
SELECT * FROM Empolyee
WHERE EmployeeID = 734;
DELETE FROM Empolyee
WHERE EmployeeID = 734;
```
# The Data Definition Language
### SQL Statement Types
**Data Manipulation**
Select  
Insert  
Update  
Delete
**Data Definition**
Create
Alter  
Drop
```sql
CREATE table (column definitions);
```
```sql
CREATE Empolyee (EmpolyeeID INTEGER PRIMARY KEY, FirstName VARCHAR(35) NOT NULL, LastName VARCHAR(100) NOT NULL, Department VARCHAR(30) NULL, Salary INTEGER);
```
```sql
ALTER TABLE Empolyee ADD Email VARCHAR(100);
```
```sql
DROP TABLE Empolyee;
```
**Data Control**
Grant  
Revoke
