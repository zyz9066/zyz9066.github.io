---
layout: post
title:  "Hash-Based Data Structures"
date:   2018-04-30
tags:  [data structure]
---
# Using associative arrays
### Associative arrays

|0|Alabama|
|1|Alaska|
|2|Arizona|
|3|Arkansas|
|4|California|
|5|Colorado|
|...|...|

key / value pair

|AL|Alabama|
|AK|Alaska|
|AZ|Arizona|
|AR|Arkansas|
|CA|California|
|CO|Colorado|
|...|...|

### Sorting associative arrays

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

**keys must be unique**

|AL|Alabama|
|AK|Alaska|
|AZ|Arizona|
|AR|Arkansas|
|CA|California|
|CO|Colorado|
|...|...|

**Value can be objects**

|ZJ|{id:654,lastname:Zbigniew,firstname:Jane,hiredate:1/1/2001}|
|AT|{id:100,lastname:Adams,firstname:Thomas,hiredate:12/14/2004}|
|TR|{id:123,lastname:Thompson,firstname:Roy,hiredate:9/9/2011}|
|SS|{id:121,lastname:Smith,firstname:Sam,hiredate:11/1/2000}|
|TF|{id:004,lastname:Von Trapp,firstname:Florence,hiredate:7/1/2001}|
|SG|{id:407,lastname:Smith,firstname:Grace,hiredate:2/13/2009}|
|...|...|

### Object keys, primitive values

|a0|123|
|a1|234|
|a2|456|
|a3|789|
|a4|999|
|a5|9742|

### Associative arrays - language support

|Java|`HashMap`, `HashTable`|
|C#|`Hashtable`, `Dictionary`|
|Python|`dict`|
|Ruby|`Hash`|
|Objective-C|`NSDictionary`|
|C++|`std::unordered_map`|

# Understanding hash functions
### Hash values
~~~~~~~
obj-->| hash function |-->3646143
~~~~~~~
**Hashing is not Encryption**
* Hashing functions are typically one-way (not *invertible*)
* Information is lost when hashing

### Hashing function -example
{% highlight java %}
Public Class Person {
    String firstname;
    String lastname;
    Date birthDate;
}
@Override
public int hashCode() {
    // code to add all numeric values
    // ...
    return hashvalue;
}
{% endhighlight %}

|Sam|19 + 1 + 13 = 33|
|Jones|10 + 15 + 14 + 5 + 19 = 44|
|04/04/1990|4 + 4 + 1990 = 1998|

hash = 33 + 44 + 1998 = 2075

**Hashing rules**
* Hashing should be deterministic under the same context
* Two objects that are *equal* should return the same hash
* But the same hash *may* also result from different objects - **Hashing Collision**

# Using hash tables
### Creating hash tables

|0||
|1||
|...|...|
|998||
|999||

`myHT.add("AZ","Arizona");`
~~~~~~~
"AZ"-->| hash function|-->72930 % 999 = remainder 5
~~~~~~~

|0||
|1||
|2||
|3||
|4||
|5|Arizona|
|...|...|
|998||
|999||

~~~~~~~
"CA"-->| hash function|-->65936 % 999 = remainder 2
~~~~~~~

|0||
|1||
|2|California|
|3||
|4||
|5|Arizona|
|...|...|
|998||
|999||

`result = myHT.get("AZ");`
~~~~~~~
"AZ"-->| hash function|-->72930 % 999 = remainder 5
~~~~~~~

|0||
|1||
|2|California|
|3||
|4||
|5|**Arizona**|
|...|...|
|998||
|999||

### Managing collisions
`myHT.add("MN","Minnesota");`
~~~~~~~
"MN"-->| hash function|-->66938 % 999 = remainder 5
~~~~~~~

|0||
|1||
|2|California|
|3||
|4||
|5|Arizona / Minnesota|
|...|...|
|998||
|999||

separate chaining
~~~~~~~
linked list-->AZ Arizona-->MN Minnesota
~~~~~~~
# Supporting hashing
Default hash behavior

|Java|`hashCode()`|
|Objective-C|`-hash`|
|C#|`GetHashCode()`|
|Ruby|`hash()`|
|Python|`hash()`|
|C++|`std::hash`|

**Hashing in custom classes**
* Default equality behavior checks identity
* Can be overridden to check internal state
* If you redefine equality, redefine hashing - If two objects are *equal* they must return the same hash
* This behavior is already provided for string objects

# Language support for hash tables

### Associative arrays - language support

|Java|[`HashMap`](https://docs.oracle.com/javase/7/docs/api/java/util/HashMap.html "HashMap<K,V>"), [`HashTable`](https://docs.oracle.com/javase/7/docs/api/java/util/Hashtable.html "Hashtable<K,V>"), [`ConcurrentHashMap`](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html "ConcurrentHashMap<K,V>")|
|C#|[`Hashtable`](https://msdn.microsoft.com/en-us/library/system.collections.hashtable(v=vs.110).aspx "Hashtable"), [`Dictionary<>`](https://msdn.microsoft.com/en-us/library/xfhwa508(v=vs.110).aspx "Dictionary<TKey, TValue>"), [`StringDictionary`](https://msdn.microsoft.com/en-us/library/system.collections.specialized.stringdictionary(v=vs.110).aspx "StringDictionary"), [`SortedDictionary<>`](https://msdn.microsoft.com/en-us/library/f7fta44c(v=vs.110).aspx "SortedDictionary<TKey, TValue>")|
|Python|[`dict`](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict "dict")|
|Ruby|[`Hash`](http://ruby-doc.org/core-2.5.0/Hash.html "Hash")|
|Objective-C|[`NSHashTable`](https://developer.apple.com/documentation/foundation/nshashtable "NSHashTable"), [`NSDictionary`](https://developer.apple.com/documentation/foundation/nsdictionary "NSDictionary"), [`NSMutableDictionary`](https://developer.apple.com/documentation/foundation/nsmutabledictionary "NSMutableDictionary")|
|C++|`std::unordered_map`|

Ruby: `Hash` - A Hash is a dictionary-like collection of unique keys and their values. Also called associative arrays, they are similar to Arrays, but where an Array uses integers as its index, a Hash allows you to use any object type.

Java: [Interface Map<K,V>](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html "Map<K,V>")