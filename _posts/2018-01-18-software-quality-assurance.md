---
layout: post
title:  "Software Quality Assurance"
date:   2018-01-18
tags:  [quality assurance]
---
# Types of Quality Engineers
<!-- How to think about Quality -->
## Traditional disciplines in software development
### Common Terms
* **Black box**: product management $$\cap$$ quality  
Test through user interface
* **White box**: development $$\cap$$ quality  
Testing at code level, under the hood
* **Grey box**: product management $$\cap$$ development $$\cap$$ quality  
Looking from the outside, but with knowledge internals

Product Management  
Development  
Quality
<!-- Black-box testing: More than just clicking buttons
 White box: Thinking about your internals from a test perspective
 Gray box: Thinking past the user interface -->
# Defining a Common Language
## Understanding your project and quality goals
$$\begin{array}{lcr}
\hline
\large\alpha &\large\beta &\large release\\
\small high\;priority &\small medium\;priority &\small low\;priority
\end{array}$$
## Breaking down and ranking issues by severity
* Crash
* Non-Functioning
* Incorrectly Functioning
* Incorrectly Functioning with Workaround
* Performance
* Cosmetic

## Using a matrix to define priorities

| | 100% - 75% | 75% - 50% | 50% - 25% | < 25% |
|:-|:-:|:-:|:-:|:-:|
|Crash|Priority 1|Priority 1|Priority 1|Priority 1|
|Non-Functioning|Priority 1|Priority 1|Priority 1|Priority 2|
|Incorrectly Functioning|Priority 1|Priority 1|Priority 2|Priority 2|
|Incorrectly Functioning with Workaround|Priority 1|Priority 2|Priority 2|Priority 3 or 4|
|Performance|Priority 2|Priority 2|Priority 3 or 4|Priority 3 or 4|
|Cosmetic|Priority 2|Priority 3 or 4|Priority 3 or 4| Priority 3 or 4 |

# Tracking Systems
## Bug Base
A system for keeping track of every bug that's logged in a database
* Atlassian JIRA
* Bugzilla
* FogBugz
* Apache Bloodhound
* Assembla
* Microsoft CodePlex
and more...

* Project name
* Issues
* Feature/Ownership areas
* Defect frequency
* Priority
* Issue template
* Target fix date
* Build information
* Conversation
* Attachments
* Workflow management
* Linking terms and bugs

## Test case management systems
* Ease of use
* Easy adoption
* Transparency
* Easily assign cases to suites
* Easy to determine what to run
* Easily assign test passes
* Real time reports

|TCM|
|:-:|
|Test Case|

|Bugbase|
|:-:|
|Bug Report|

## Recording defects

|Bug Report|
|:-|
|**Summary**: Invisible tripping hazard exists in room<br><br>1. Walk around room<br><br>**Results**: Eventually you'll hit the object and trip|

|Bug Report|
|:-|
|**Summary**: Invisible tripping hazard exists in room<br><br>1. Start at the bottom left corner of the room<br>2. Walk towards the top left corner of the room<br><br>**Results**: Halfway across the room you'll trip over the invisible object|

## Bug Workflow
Reported ---> Assigned ---> Fixed ---> Closed

Reported ---> Assigned ---> Reporter verifies if fixed -Y-> Closed

Customer Bug ---> CS Org  
Customer ---> CS Org ---> Reproducible on live system? -Y-> Reproducible on test system? -Y-> Developer ---> Fix ---> Fixed? -Y-> Closed  
Customer ---> CS Org ---> Reproducible on live system? -Y-> Reproducible on test system? ---> Internal Review
## Bug Model

|Week|Number of Bugs Logged|Number of Bugs Fixed|Bug Count|
|:-:|:-:|:-:|:-:|
|1|20|10|10|
|2|20|10|20|
|3|20|10|30|
|4|20|10|40|
|5|20|10|50|
|6|20|10|60|
|7|20|10|70|
|8|20|10|80|
|9|20|10|90|
|10|20|10|100|
|11|20|10|110|
|12|20|10|120|

### What to plan for
* Relative flow of bug reports
* Developer priorities
* Management evaluation

|Week|Number of Bugs Logged|Number of Bugs Fixed|Bug Count|Actual|
|:-:|:-:|:-:|:-:|:-:|
|1|30|10|20|22|
|2|30|10|40|45|
|3|25|10|55|65|
|4|25|20|60|70|
|5|20|20|60|65|
|6|40|20|80|100|
|7|30|20|90|120|
|8|20|20|90|100|
|9|20|30|80|90|
|10|15|35|60|80|
|11|10|35|35|40|
|12|5|40|0|0|

## Interpreting bug models
**Bug Count**: Projected, Actual
# Areas of Focus
## Testing core functionality

|Username|Password|Result|
|:-:|:-:|:-:|
|Valid|Valid|Success|
|Invalid|Invalid|Fail|
|Valid|Invalid|Fail|
|Invalid|Valid|Fail|

### Test Cases
1. Valid log in credentials result in a successful log in
2. Invalid user name AND invalid password result in an unsuccessful attempt to log in
3. Invalid password with a valid user name should also fail
4. Invalid user name and a valid password won't allow us to advance
5. User neglects to enter any user name
6. User forgets to enter a password
7. User attempts to log in without entering anything at all

## Identifying possible user scenarios
### Text Editor
* Users can enter text
* Users can cut, copy paste
* Ability to save
* Change font and text size
* Bold and italic options

What are the install options?  
How is the application uninstalled?
### Basic Text Editor
* Alternative input methods
* Screen readers
* Multiple language support

### Testing Environment
* Workstation vs. tablet
* Low memory
* Slow bandwidth

## Back-end testing
### Common Backend Tests
* Load tests
* Performance tests
* Stress tests

How does my application respond with X users?  
<big>**Concurrent Users**</big>  
Users with active connection to your site at the same time
**Simultaneous Users**
Users performing same action at same time
### Performance Test
* **Time for an operation to complete under different kinds of load**
Reading from database
Writing to database

How long does it take for this process to execute?
### Stress Test
* Maximum number of users your application can handle
* Extent of scale
* Validate backup systems

How many users can my application handle before it fails?
## Load testing

|Client|
|:-:|
|Browser|

Internet

Loader Balancer

|Server|
|:-:|
|Web Server<br>Logic<br>Database|

# Automation
## Automatic recording of defects

|A|`id: btn001`<br>`state: normal`<br>`color: gray`|
|B|`id: btn002`<br>`state: normal`<br>`color: gray`|
|C|`id: btn003`<br>`state: normal`<br>`color: gray`|

|A|`id: btn001`<br>`state: normal`<br>`color: gray`|
|B|`id: btn002`<br>`state: clicked`<br>`color: blue`|
|C|`id: btn003`<br>`state: normal`<br>`color: gray`|

## Putting unit tests in context
Garden
```java
Class GreenBeans {}
Class Tomatoes {color="red";}
Class Corn {}
Class Peas {}
```
<!-- Testing the interaction between objects -->
