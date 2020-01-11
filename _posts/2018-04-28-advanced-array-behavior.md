---
layout: post
title:  "Advanced Array Behavior"
date:   2018-04-28
tags:  [data structure]
---
# Resizable arrays

### Simple fixed-size arrays: Java
{% highlight java %}
string fixedArray = new String[3];
fixedArray[0] = "This";
fixedArray[1] = "Cannot";
fixedArray[2] = "Grow";
{% endhighlight %}
### Resizable arrays: Java
{% highlight java %}
// need to import
import java.util.*;
// create ArrayList of Strings
List<String> resizable = new ArrayList<String>();
    
resizable.add("This");
resizable.add("Is");
resizable.add("Resizable");
{% endhighlight %}
### Fixed/resizable arrays: Objective-C
{% highlight c %}
// simple arrays exist as in C
int myArray[3];
myArray[0] = 99; // etc.
{% endhighlight %}
{% highlight objective_c %}
// NSArray used for arrays of objects - fixed size
NSArray *myFixedArray = @[@"one",@"two",@"three"];
// NSMutableArray is the resizable version
NSMutableArray *resizable = [[NSMutableArray alloc]init];
[resizable addObject:@"one"];
[resizable addObject:@"two"];
[resizable addObject:@"three"];
{% endhighlight %}
### Adding new elements: location?

|0|123|
|1|9742|
|2|789|
|3|234|
|4|456|
|5|5678|
|6|21|
|7|42|
|8|123|

`myArray.add(999);`

|0|123|
|1|9742|
|2|789|
|3|234|
|4|456|
|5|5678|
|6|21|
|7|42|
|8|123|
|9|999|

`myArray.add(999,2);`

|0|123|
|1|9742|
|2|999|
|3|789|
|4|234|
|5|456|
|6|5678|
|7|21|
|8|42|
|9|123|

### Appending items at end of array

| Java | `add(value)` |
| Objective-C | `addObject:value` |
| JavaScript | `push(value)` |
| Ruby | `push(value)` |
| Python | `append(value)` |

### Inserting items at specific index

| Java | `add(index,value)` |
| Objective-C | `addObject:value atIndex:index` |
| JavaScript | `splice(index,items_to_remove,items_to_insert)` |
| Ruby | `insert(index,value)` |
| Python | `insert(index,value)` |

### Removing items from an array

| Java | `remove(index)` |
| Objective-C | `removeObjectAtIndex:index` |
| JavaScript | `pop / splice` |
| Ruby | `pop / delete_at` |
| Python | `pop / remove` |

### The five requirements of any data structure
* How to **Access** (one item / all items)
* How to **Insert** (at end / at position)
* How to **Delete** (from end / from position)
* How to **Find** (if exists / what location)
* How to **Sort** (sort in place / created sorted version)

# Sorting arrays

|0|123|
|1|9742|
|2|999|
|3|789|
|4|234|
|5|456|

`myArray.sort();`

|0|123|
|1|234|
|2|456|
|3|789|
|4|999|
|5|9742|

### Sorting custom objects

|0|{id:654,lastname:Zbigniew,firstname:Jane,hiredate:1/1/2001}|
|1|{id:100,lastname:Adams,firstname:Thomas,hiredate:12/14/2004}|
|2|{id:123,lastname:Thompson,firstname:Roy,hiredate:9/9/2011}|
|3|{id:121,lastname:Smith,firstname:Sam,hiredate:11/1/2000}|
|4|{id:004,lastname:Von Trapp,firstname:Florence,hiredate:7/1/2001}|
|5|{id:407,lastname:Smith,firstname:Grace,hiredate:2/13/2009}|

`myArray.sort(); // need comparator / compare function`

### Comparator / compare function
~~~~~~~
PseudoCompare (Employee a, Employee b)
    // less than
    if a.lastname < b.lastname return -1
    // greater than
    if a.lastname > b.lastname return 1
    if a.lastname == b.lastname
        // less than
        if a.firstname < b.firstname return -1
        // greater than
        if a.firstname > b.firstname return 1
        // equal
        if a.firstname == b.firstname return 0
    end if
end
~~~~~~~
# Searching arrays

|14|13|12|11|11|12|12|14|14|14|18|20|21|20|20|19|19|17|16|16|16|16|15|15|
|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|

**linear (sequential) search: O(n) complexity**
~~~~~~~
set i to 0
while i < array.length
    if array[i] == 19
        return true
    end if
    add 1 to i
end while
return false
~~~~~~~
# Using built-in search behavior

|14|13|12|11|11|12|12|14|14|14|18|20|21|20|20|19|19|17|16|16|16|16|15|15|
|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|

{% highlight java %}
// for simple yes/no result
if (myArray.contains(19)) {
    log("Yes, it exists.");
}
// for specific location
int result = myArray.indexOf(19);
if (result != -1) {
    log("The value is located at position: " + result);
} else {
    log("The value was not found.");
}
{% endhighlight %}
### Searching for existence / location

| Java | `contains` | `indexOf` |
| Objective-C | `containsObject` | `indexOfObject` |
| JavaScript | | `indexOf` |
| Ruby | | `index / find_index` |
| Python | | `index` |
| C# | `contains` | `indexOf` |

# Using binary searching
### Binary searching
Values in array are in ascending or descending order:

|1|11|11|11|11|12|12|14|14|14|18|20|21|21|22|29|29|37|46|46|56|56|65|65|
|0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|

**AKA half-interval search / Divide-and-conquer algorithm**
### Binary searching - language support

| Java | `binarySearch` |
| Objective-C | `indexOfObject:inSortedRange` |
| JavaScript | n/a |
| Ruby | `bsearch` |
| C++ | `binary_search` |
| C# | `Array.BinarySearch` |

**Binary searches "only" work on ordered data**