---
layout: post
title:  "Database Options"
date:   2018-01-18
tags:  [databases]
---
# Desktop Databases Systems
[Access](https://products.office.com/en-us/access)  
[FileMaker](http://www.filemaker.com/products/filemaker-pro-advanced/)  
[OpenOffice](https://www.openoffice.org/product/index.html)
* Aimed at power users
* A step up from spreadsheets

Pros
* Simple to install
* Easy to use
* Templates for starting
* Tools for setup
* Options for reporting

Cons
* Can't accommodate many users
* Stored in a single file
* Won't support very large data
* Can't serve as a website database

# Relational Database Management Systems
### RDBMS
All based on work by E. F. Codd.

|Name|Vendor|Released|AdminApplication|License||
|:-:|:-:|:-:|:-:|:-:|:-:|
|Oracle|Oracle|1979|Oracle SQL Developer|Commercial||
|DB2|IBM|1983|IBM Data Studio|Commercial||
|SQL Server|Microsoft|1989|SQL Server Management Studio|Commercial||
|MySQL|Oracle|1994|MySQL Workbench|Open Source||
|(etc.)|...|...|...|...|...|

[Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
[Amazon RDS Pricing](https://aws.amazon.com/rds/pricing/)
[SQL Server Express](https://www.microsoft.com/en-us/sql-server/sql-server-editions-express)
[Oracle Database Express](http://www.oracle.com/technetwork/database/database-technologies/express-edition/overview/index.html)
[DB2 Express-C](https://www.ibm.com/developerworks/downloads/im/db2express/)
# Object-based and XML-based databases
### XML Database Systems

|Name|License|QueryLanguage|
|:-:|:-:|:-:|
|BaseX|Open Source|XQuery|
|Sedna|Open Source|XQuery|
|eXist|Open Source|XQuery|

```xml
<?xml version="1.0.7">
<library>
  <course id="fop003">
    <author>Allardice, Simon</author>
    <title>Foundations of Programming: Databases</title>
    <genre>Developer</genre>
    <date_published>2015-08-30</date_published>
    <description>Getting started with databases and database technologies.</description>
  </course>
  <course id="java001">
    <author>Gassner, David</author>
    ...
```
### RDBMS XML Support

|Name|XML Column Type?|
|:-:|:-:|
|Oracle|Yes|
|DB2|Yes|
|SQL Server|Yes|
|MySQL|No-store as text|

### Object-Oriented Database Systems

|Name|
|:-:|
|Objectivity/DB|
|VelocityDB|
|Versant|

### Object-Relational Mapping (ORM)

|ORM Framework|Language|
|:-:|:-:|
|Hibernate|Java|
|Core Data|Objective-C|
|ActiveRecord|Ruby|
|NHibernate|C#/VB.NET|

# NoSQL Database Systems
"Not only SQL"
### Databases in NoSQL Category
* CouchDB
* MongoDB
* Apache Cassandra
* Hypertable
* HBase
* Neo4j
* BigTable
* Riak
* Project Voldemort
* Redis
And many more

Features of NoSQL Databases **May** Include
* Not using SQL
* Not being table based
* Not relationship oriented
* Not ACID
* No formal schema
* Oriented to web development
* Oriented to large-scale deployment
* Often open source

### Document Stores
* Documents, not rows and columns
* Examples: CouchDB and MongoDB
```
{
    "title": "Foundations of Programming: Databases",
    "rating": 10
}
```
```
{
    "LastName": "Brown",
    "FirstName": "Michelle",
    "Email": [
      {
        "type": "home",
        "number": "michelleb@...com"
      },
      {
        "type": "work",
        "number": "mbrown@acme...com",
        "verified": false
      }
    ],
    "DateHired": "02-17-2009",
    "Department": "Production"
}
```
### Key-Value Stores
* **Everything** stored as a key-value pair
* Examples: MemcacheDB, Riak, and Project Voldemort

|key|value|
|:-:|:-:|
|name1|bob|
|color|red|
|company4534_name|Microsoft|
|company4556_name|Apple|
|course_43fe6fe|<small>{"title": "Foundations of Programming: Databases", "rating": 10}</small>|
|u473642_photo|(binary data)|
|...|...|

### Graph Database
* **Everything** stored as small connected nodes, with relations
* Examples: Neo4j, AllegroGraph, and DB2 NoSQL Graph Store

### Reasons to Choose a NoSQL Database
* Do you need a **flexible schema**?
* Do you have **vast amounts of data**?
[HBase Architecture](http://hbase.apache.org/book.html#arch.overview)
>First, make sure you have enough data. If you have hundreds of millions or billions of rows, then HBase is a good candidate.
* Do you value **scaling** over **consistency**?
