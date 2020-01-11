---
layout: post
title:  "Database Modeling: Optimization"
date:   2018-01-17
tags:  [databases]
---
# Database Normalization
First Normal Form (1NF) ---> Second Normal Form (2NF) ---> Third Normal Form (3NF)  
"...database will comply with third normal form when every non-prime attribute of R is non-transitively dependent (i.e., directly dependent) on every candidate key of R..."
# First Normal Form
violate 1NF
# Second Normal Form
**Second normal form**: Any non-key field should be dependent on the entire primary key.  
Composite primary key
# Third Normal Form
**Third normal form**: No non-key field is dependent on any other non-key field.  
if needed, a read-only calculated column
# Database Denormalization
1NF: No repeating values and no repeating groups  
2NF: No non-key values based on just *part* of a composite key  
3NF: No non-key values based on *other* non-key values
