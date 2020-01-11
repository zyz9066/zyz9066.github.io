---
layout: post
title:  "Simple Structures and Basic Arrays"
date:   2018-04-25
tags:  [data structure]
---
# Describing simple data structure

{% highlight c %}
// first book
string bookTitle = "Dark and Stormy Night";
double bookPrice =12.95;
bool bookPublished =true;
bool bookHardback = false;
// second book
string book2Title = "Stormy Return";
double book2Price = 17.95;
bool book2Published = false;
bool bookHardback = true;
// third book
string book2Title = "Stormy Strike back";
double book2Price = 16.95;
bool book2Published = false;
bool bookHardback = true;
{% endhighlight %}

|Title|Price|Published|Hardback|
|:-:|:-:|:-:|:-:|
| Dark and Stormy Night | 12.95 | true | false |
| Stormy Returns |17.95 | false | true |
| Stormy Strike Back | 16.95 | false | true |
|-

Each row is a **record** and each cell is a **field**.
# Using C-style structs

{% highlight c %}
// define the struct
struct Book {
    String title;
    double price;
    bool isPublished;
    bool isHardback;
}
// create a variable with that struct type
Book first;
// set member variables
first.title = "Dark and Stormy Night";
first.price =12.95;
first.isPublished =true;
first.isHardback = false;
{% endhighlight %}

### Difference between structs and classes

|Struct|Class|
|:-:|:-:|
| only data - no behavior | behavior and data |
| simple creation | explicit instantiation (new, alloc) |
| value types | reference types |
| no object-oriented features | polymorphism, inheritance, etc. |
| "Plain Old Data Structure" (PODS) |  |
|-

### Plain old data structure: example
{% highlight c %}
struct Point {
    int x;
    int y;
};

Point startPosition;
startPosition.x = 50;
startPosition.y = 50;

Point finishPosition;
finishPosition.x = 500;
finishPosition.y = 100;

myObject.animate(startPosition, finishPostion);
{% endhighlight %}

{% highlight c %}
struct Color {
    int red;
    int green;
    int blue;
    int alpha;
};

Color backgroundColor;
backgroundColor.red = 255;
backgroundColor.green = 0;
backgroundColor.blue = 0;
backgroundColor.alpha = 255;

myWindow.setBackground(backgroundColor);
{% endhighlight %}

### Language support for structs

| Objective-C | As in C, used in many Apple frameworks |
| C# / other .NET | Also allows basic behavior to be added |
| Java | Do not exist - closest equivalent is lightweight class |
| Python | Do not exist |
| Ruby | Exist, though implemented as lightweight class |

# Basic arrays
### One-dimensional array
`myArray`

|0|123|
|1|9742|
|2|789|
|3|234|
|4|456|
|5|5678|
|6|21|
|7|42|
|8|123|
|9|213456|

Left column is **index**.\\
**Simple arrays**: Zero-based index, Fixed size (immutable), Specific data type.

# Multidimensional arrays
### Two-dimensional array
`my2DArray`

|0|123|456|213|33|212|342|
|1|742|273|23|2|43|13|
|2|789|43|5|67|43|322|
|3|234|567|85|355|67|86|
|4|456|34|5|6|354|5|
||0|1|2|3|4|5|

For one-dimensional data access: `int result = myArray[2];`\\
For two-dimensional data access: `int result = my2DArray[2,3];`
### Arrays of arrays

|0|123|456|213|33|212|342|
||0|1|2|3|4|5|
|1|742|273|23|2|43|13|
||0|1|2|3|4|5|
|2|789|43|5|67|43|322|
||0|1|2|3|4|5|
|3|234|567|85|355|67|86|
||0|1|2|3|4|5|
|4|456|34|5|6|354|5|
||0|1|2|3|4|5|

`int result = myArray[2,3];`\\
Result is 67.

|0|a1|b1|c1|d1|e1|f1|
|1|a2|b2|c2|d2|e2|f2|
|2|a3|b3|c3|d3|e3|f3|
|3|a4|b4|c4|d4|e4|f4|
|4|a5|b5|c5|d5|e5|f5|
|5|a6|b6|c6|d6|e6|f6|
|6|a7|b7|c7|d7|e7|f7|
||0|1|2|3|4|5|

### Two-dimensional array: example
`temperatureArray`

|0|25|23|19|17|17|16|16|18|19|20|22|25|27|30|35|38|38|37|37|36|35|33|31|27|
|1|25|23|19|18|17|16|17|18|21|24|28|31|35|38|42|45|48|48|46|42|38|35|31|28|
|2|26|22|20|20|17|16|16|20|21|21|22|24|27|30|31|33|35|35|33|30|25|22|20|18|
|3|14|13|12|11|11|12|12|14|14|14|18|20|21|20|20|19|19|17|16|16|16|16|15|15|
||0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|

It's easy to calculate the average of each row and column.

### Three-dimensional array: example
`temperatureArray2`

|0|0|25|23|19|17|17|16|16|18|19|20|22|25|27|30|35|38|38|37|37|36|35|33|31|27|
||1|25|23|19|18|17|16|17|18|21|24|28|31|35|38|42|45|48|48|46|42|38|35|31|28|
||2|26|22|20|20|17|16|16|20|21|21|22|24|27|30|31|33|35|35|33|30|25|22|20|18|
||3|14|13|12|11|11|12|12|14|14|14|18|20|21|20|20|19|19|17|16|16|16|16|15|15|
|||0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|
|1|0|25|23|19|17|17|16|16|18|19|20|22|25|27|30|35|38|38|37|37|36|35|33|31|27|
||1|25|23|19|18|17|16|17|18|21|24|28|31|35|38|42|45|48|48|46|42|38|35|31|28|
||2|26|22|20|20|17|16|16|20|21|21|22|24|27|30|31|33|35|35|33|30|25|22|20|18|
||3|14|13|12|11|11|12|12|14|14|14|18|20|21|20|20|19|19|17|16|16|16|16|15|15|
|||0|1|2|3|4|5|6|7|8|9|10|11|12|13|14|15|16|17|18|19|20|21|22|23|

Arrays of Arrays of Arrays.\\
`int result = temperatureArray[1,3,11];`\\
Result is 18.

# Jagged arrays
### Rectangular two-dimensional arrays
`int[,] my2DArray = new int[5,6];`

|0|
|1|
|2|
|3|
|4|
||0|1|2|3|4|5|

`my2DArray[0,0] = 123;`

|0|123|
|1|
|2|
|3|
|4|
||0|1|2|3|4|5|

### Using jagged arrays

|0|123|96|113|131|...|133|112|82|92|
||0|1|2|3|...|28|29|30|31|
|1|72|123|123|102|...|103|
||0|1|2|3|...|28|29|30|31|
|2|89|43|105|121|...|98|117|125|104|
||0|1|2|3|...|28|29|30|31|
|3|134|107|85|95|...|98|92|112|
||0|1|2|3|...|28|29|30|31|
|4|106|134|105|99|...|106|104|105|124|
||0|1|2|3|...|28|29|30|31|

TicketSales for every day in every month.

|0|123|96|113|131|...|133|112|82|92|
||0|1|2|3|...|28|29|30|31|
|1|72|123|123|102|...|103|
||0|1|2|3|...|28|
|2|89|43|105|121|...|98|117|125|104|
||0|1|2|3|...|28|29|30|31|
|3|134|107|85|95|...|98|92|112|
||0|1|2|3|...|28|29|30|
|4|106|134|105|99|...|106|104|105|124|
||0|1|2|3|...|28|29|30|31|

### Creating jagged arrays
~~~~~~~
int [][] ticketSales  new int[12][];
for each month in ticketSales
    if april, june, september, november
        create array of 30 elements
    else if february and leap year
        create array of 29 elements
    else if feruary and not leap year
        create array of 28 elements
    else 
        create array of 31 elements
    end if
    add array to ticketSales[months]
end for
~~~~~~~