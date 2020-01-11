---
layout: post
title:  "Domain Modeling (Modeling the App)"
date:   2018-01-12
tags:  [object oriented design]
---
<!-- Creating a conceptual model -->
# Identifying the classes
### Identifying Objects
**Use Case Scenario**: *Customer* verifies *items* in *shopping cart*. Customer provides *payment* and *address* to process *sale*. *System* validates payment information and responds with confirmation of *order*, and provides *order number* that Customer can use to check on *order status*. System will send Customer a copy of *order details* by *email*.

Noun List
* Customer
* Item
* Shopping Cart
* Payment
* Address
* Sale
* Order
* Order Number
* Order Status
* Order Details
* Email
* System

* Customer
* Item
* Shopping Cart
* Payment
* Address
* Order
* Email

### Conceptual Object Model

|Customer|

|Item|

|Shopping Cart|

|Payment|

|Address|

|Order|

|Email|

# Identifying class relationships
### Conceptual Object Model
![]({{site.baseurl}}/images/object oriented design/conceptual model.jpg)
# Identifying class responsibilities
**Use Case Scenario**: Customer *verifies items* in shopping cart. Customer *provides payment and address* to *process sale*. System *validates payment* information and responds by *confirming order*, and *provides order number* that Customer can use to *check on order status*. System will *send* Customer a copy of order details by *email*.
* Verify items
* Provide payment and address
* Process sale
* Validate payment
* Confirm order
* Provide order number
* Check order status
* Send order details email

### Assigning Responsibilities
![]({{site.baseurl}}/images/object oriented design/class responsibility.jpg)
### Working with "System"
**Use Case Scenario**: Customer verifies items in shopping cart. Customer provides payment and address to process sale. *System validates payment* information and responds by confirming order, and provides order number that Customer can use to check on order status. *System will send Customer a copy of order details by email*.
![]({{site.baseurl}}/images/object oriented design/global master.jpg)
Avoid global master objects, responsibilities should be well distributed.
# CRC cards
Class name\\
$$\begin{array}{l|l}
Responsibilities & Collaborators
\end{array}$$

Payment\\
$$\begin{array}{l|l}
{Store\; payment\; details\\ Validate\; payment} & Order
\end{array}$$

Customer\\
$$\begin{array}{l|l}
& {Shopping\; cart\\ Order}
\end{array}$$

Shopping cart\\
$$\begin{array}{l|l}
{Display\; totals} & {Customer\\ Item}
\end{array}$$

Item\\
$$\begin{array}{l|l}
{Store\; item\; details} & {Shopping\; cart\\ Order}
\end{array}$$

Address\\
$$\begin{array}{l|l}
{Keep\; address\; details\\ Validate\; address\; information\\ Verify\ zip\; code} & {Customer\\ Order}
\end{array}$$

Email\\
$$\begin{array}{l|l}
Keep\; email\; details & Send
\end{array}$$

Order\\
$$\begin{array}{l|l}
{Process\; order\\ Confirm\; order\\ Get\; order\; number\\ Get\; status\\Create\; confirmation\; email} & {Customer\\ Item\\ Email\\ Address\\ Payment}
\end{array}$$
