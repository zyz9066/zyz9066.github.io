---
layout: post
title:  "Creating Classes"
date:   2018-01-13
tags:  [object oriented design]
---
# Class diagrams

|Class name|
|:-:|
|Attributes|
|Operations|

|Product|
|-|
|`- name: String = "New Product"`<br>`- isActive: Boolean`<br>`- launchDate: Date`<br>`- itemNumber: Integer`|
|`+ getName(): String`<br>`+ setActive(Boolean)`<br>`+ getProductDetails(): String`<br>`+ displayProduct()`<br>`- formatProductDetails(): String`|

Avoid building plain data structures

|Customer|
|-|
|`customerId`<br>`customerName`<br>`email`<br>`address`<br>`phone`<br>`company`<br>`firstPurchaseDate`<br>`customerContact`<br>...|
||

|Order|
|-|
|`orderNumber`<br>`orderDate`<br>`orderAmount`<br>`orderStatus`<br>`orderType`|
||

# Converting class diagrams to code

|Spaceship|
|-|
|`+ name: String`<br>`- shieldStrength: Integer`<br>...|
|`+ fire(): String`<br>`+ reduceShields(Integer)`<br>...|

### Simple class in Java
{% highlight java %}
public class Spaceship {

    // instance variables
    public String name;
    private int shieldStrength;
    
    //methods
    public String fire() {
        return "Boom!";
    }
    
    public void reduceShields(int amount) {
        shieldStrength -= amount;
    }
    
}
{% endhighlight %}
### Simple class in C#
{% highlight c# %}
public class Spaceship {

    // instance variables
    public String name;
    private int shieldStrength;
    
    //methods
    public String fire() {
        return "Boom!";
    }
    
    public void reduceShields(int amount) {
        shieldStrength -= amount;
    }
    
}
{% endhighlight %}
### Simple class in VB.NET
{% highlight vb %}
Public Class Spaceship

    ' instance variables
    Public Name As String
    Private ShieldStrength As Date
    
    ' methods
    Public Function Fire() As String
        Return "Boom!";
    End Function
    
    Public Function ReduceShields(Amount as Integer)
        ShieldStrength -= Amount;
    End Function
    
End Class    
{% endhighlight %}
### Simple class in Ruby
{% highlight ruby %}
class Spaceship

    # instance variables
    @name
    @shield_strength
    
    # methods
    def fire
        return "Boom!"
    end
    
    def reduce_shields(amount)
        shield_strength -= amount;
    end

end
{% endhighlight %}
### Simple class in Objective-C
interface
{% highlight objective_c %}
@interface Spaceship : NSObject {
    @public
    NSString *name;
    @private
    int shieldStrength;
}

// method declarations
-(NSString *) fire;
-(void) reduceShields:(int)amount;

@end
{% endhighlight %}
implementation
{% highlight objective_c %}
@implementation Spaceship

-(NSString *) fire {
    return @"Boom!";
}
-(void) reduceShields:(int)amount {
    shieldStrength -= amount;
}
@end
{% endhighlight %}
# Exploring object lifetime
### Instantiation
* Java: `Customer fred = new Customer();`
* C#: `Customer fred = new Customer();`
* VB.NET: `Dim fred As New Customer`
* Ruby: `fred = Customer.new`
* C++: `Customer *fred = new Customer();`
* Objective-C: `Customer *fred = [[Customer alloc]] init;`

### Constructors

|Spaceship|
|-|
|`name: String`<br>`shieldStrength: Integer`|
|`fire(): String`<br>`reduceShields(Integer)`|

`Spaceship excelsior = new Spaceship();`

|object: excelsior|
|-|
|`name`: null<br>`shieldStrength`: 0|

### Constructor Example
{% highlight java %}
public class Spaceship {

    // instance variables
    public String name;
    private int shieldStrength;
    
    // constructor method
    public Spaceship() {
        name = "Unnamed ship";
        shieldStrenghth = 100;
    }
    // overload constructor
    public Spaceship(String n) {
        name = n;
        shieldStrenghth = 200;
    }
    // other methods
    public String fire() {
        return "Boom!";
    }
    
    public void reduceShields(int amount) {
        shieldStrength -= amount;
    }
    
}
{% endhighlight %}
`Spaceship excelsior = new Spaceship();`

|object: excelsior|
|-|
|`name`: Unnamed ship<br>`shieldStrength`: 100|

`Spaceship excelsior = new Spaceship("Excelsior 2");`

|object: excelsior|
|-|
|`name`: Excelsior 2<br>`shieldStrength`: 200|

Constructors in UML

|Spaceship|
|-|
|`name: String`<br>`shieldStrength: Integer`|
|`Spaceship()`<br><br>`fire(): String`<br>`reduceShields(Integer)`|

Multiple Constructors in UML

|Spaceship|
|-|
|`name: String`<br>`shieldStrength: Integer`|
|`Spaceship()`<br>`Spaceship(String)`<br>`fire(): String`<br>`reduceShields(Integer)`|

### Destructors / Finalizers
* Called when an object is being deleted / deallocated / released
* Use for releasing resources

# Using static / shared members

|SavingsAccount|
|-
|`accountNumber`<br>`balance`<br>**`interestRate`**|
|`deposit()`<br>`withdraw()`|

|A7652<br>$500<br>**0.85%**<br><br>`deposit()`<br>`withdraw()`|

joeAcct

|B2311<br>$50000<br>**0.85%**<br><br>`deposit()`<br>`withdraw()`|

aliceAcct

|S2314<br>$7500<br>**0.85%**<br><br>`deposit()`<br>`withdraw()`|

samAcct

**static, shared, class-level**
### Creating static variables
{% highlight java %}
public class SavingsAccount {

    // instance variables
    public String accountNumber;
    private Money balance;
    // static variable
    public static float interestRate;
    
    // other code omitted
}
{% endhighlight %}
{% highlight vb %}
' VB.NET - shared variables
Public Shared interestRate As Float
{% endhighlight %}
{% highlight ruby %}
# Ruby - class level variables
@@interestRate
{% endhighlight %}
Use the name of the class to access, `joeAcct.accountNumber`/`aliceAcct.accountNumber`/`samAcct.accountNumber`
{% highlight java %}
SavingsAccount.interestRate = .85;
{% endhighlight %}
### Creating static methods
{% highlight java %}
public class SavingsAccount {

    // instance variables
    public String accountNumber;
    private Money balance;
    // public (accessible) static variable
    public static float interestRate;
    
    // public static methods
    public static setInterestRate(float r) {
        // add code to log any change
        interestRate = r;
    }
    
    public static getInterestRate() {
        return interestRate;
    }
    
    // other code omitted
}
{% endhighlight %}
{% highlight java %}
public class SavingsAccount {

    // instance variables
    public String accountNumber;
    private Money balance;
    // changed to private
    private static float interestRate;
    
    // public static methods
    public static setInterestRate(float r) {
        // add code to log any change
        interestRate = r;
    }
    
    public static getInterestRate() {
        return interestRate;
    }
    
    // other code omitted
}
{% endhighlight %}
`SavingsAccount.setInterestRate(0.9);`
### Showing static members in UML

|SavingsAccount|
|-
|`accountNumber`<br>`balance`<br><u>interestRate</u>|
|`deposit()`<br>`withdraw()`<br><u>setInterestRate()</u><br><u>getInterstRate()</u>|