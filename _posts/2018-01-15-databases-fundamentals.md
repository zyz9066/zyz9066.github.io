---
layout: post
title:  "Database Fundamentals"
date:   2018-01-15
tags:  [databases]
---
# Relational database features
Database: tables
### Table
Rows, Columns

|FirstName<br><small>(text)</small>|LastName<br><small>(text)</small>|HireDate<br><small>(date)</small>|Grade<br><small>(numeric)</small>|Salary<br><small>(currency)</small>|
|:-:|:-:|:-:|:-:|:-:|
|Alice|Mann|4/4/2009|4|75000|
|James|Black|3/1/2000|4|75000|
|Calista|Guerra|10/1/2006|6|80000|
|Fay|Fitzgerald|7/21/2002|7|100000|

By defining columns, we're imposing rules on the data they store.  
**Tables** and **columns** are defined up front. Day-to-day use is in creating and updating **rows**
# Unique Values and Primary Keys
A **key** identifies one particular row in a table.  
Unique / Not Unique

|EmployeeID<br><small>(numeric, unique)</small>|FirstName<br><small>(text)</small>|LastName<br><small>(text)</small>|HireDate<br><small>(date)</small>|Grade<br><small>(numeric)</small>|Salary<br><small>(currency)</small>|SocialSecurity<br><small>(text, unique)</small>|
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|507|Alice|Mann|4/4/2009|4|75000|55-65-1231|
|602|James|Black|3/1/2000|4|75000|55-65-1232|
|312|Calista|Guerra|10/1/2006|6|80000|54-23-1255|
|78|Fay|Fitzgerald|7/21/2002|7|100000|89-92-2341|
|523|John|Bowen|11/11/2011|3|45000|43-23-1234|

Primary Key  
Generated primary keys are also sometimes called **synthetic keys** or **surrogate keys**.
# Defining Table Relationships
Customer, Order, Product

Customer Table

|CustomerID|FirstName|LastName|Email|Address|...|
|:-:|:-:|:-:|:-:|:-:|:-:|
|367|Michelle|Blackwell|mblackwell@...|22 Acacia|...|
|368|Lynn|Allen|la1942@...|1016B 1st...|...|
|369|Lee|Stout|lee@...|47 Main St|...|

Order Table

|OrderID|Date|Quantity|TotalDue|CustomerID|
|:-:|:-:|:-:|:-:|:-:|
|1198|3/1/2011|17|$340.00|367|
|1199|3/2/2011|47|$902.00|367|
|1200|3/2/2011|104|$1500.00|368|

Foreign Key (not unique)  
1 ---> $$\infty$$
# Many-to-Many Relationships

Author Table

|AuthorID|FirstName|LastName|Email|...|
|:-:|:-:|:-:|:-:|:-:|
|445|Michelle|Blackwell|mblackwell@...|...|
|446|Lynn|Allen|la1942@...|...|
|447|Lee|Stout|lee@...|...|

AuthorBook Table (Junction or linking table)

|AuthorID|BookID|
|:-:|:-:|
|447|1145|
|445|1145|
|446|1146|
|447|1147|

Book Table

|BookID|Title|PubDate|LastPrice|
|:-:|:-:|:-:|:-:|
|1145|Designing Databases|3/1/2012|$45.00|
|1146|SQLite Made Simple|4/11/2012|$39.95|
|1147|Pocket Guide to SQL|5/21/2012|$19.95|

# Transactions and the ACID test
Banking Transaction
### The ACID Test
* Atomic
* Consistent
* Isolated
* Durable

# Introduction to Structured Query Language (SQL)
* SQL
* Microsoft SQL Server
* MySQL
* PostgreSQL
* SQLite
* T-SQL
* PL-SQL
* (etc.)

SQL is a **declarative query language**, not a procedural, imperative language.

```
for each b in Books
  if price > 40
    add b to expensive_books_array
  else
    ignore
  end
end

return expensive_books_array
```
"I want all books more than $40"
```sql
SELECT * FROM Books WHERE ListPrice > 40
```
**C**reate  
**R**ead  
**U**pdate  
**D**elete
