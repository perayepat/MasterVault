# Overview 
![[Pasted image 20220217191516.png]]
![[Pasted image 20220217191540.png]]
- Serial - working in a linear manner 
- Parallel - Breaking up data and working on it separately 
- Deterministic - Each step executed with an exact decision 
- non-Deterministic - gets more accurate over time 

## Common Algorithms 
![[Pasted image 20220217191839.png]]
![[Pasted image 20220217191858.png]]
![[Pasted image 20220218114558.png]]
 **Design Patterns Will be looking at**
 ![[Pasted image 20220218114804.png]]
 **Design Principles**
 ![[Pasted image 20220218114841.png]]
 Principles are guidelines 
 ![[Pasted image 20220218114912.png]]
 Move the code that is going to change from the code that stays the same. 
 ![[Pasted image 20220218115003.png]]

 




# Strategy Pattern
## Overview 
Used in making weapons in a game 
![[Pasted image 20220218123123.png]]
Solves the problem of having multiple variations of the same type of object
![[Pasted image 20220218123451.png]]
Very Little duplications of code and if the fire damage needs to be changed it can be changed in one class
![[Pasted image 20220218123634.png]]
Generic Classes set by a constructor 
![[Pasted image 20220218123655.png]]
![[Pasted image 20220218123741.png]]
![[Pasted image 20220218123830.png]]

## Revising Inheritance 
Designing a duck simulator 
![[Pasted image 20220218120202.png]]
We have a problem because of the rubber duck 
**Feature Request for the adding flying**
![[Pasted image 20220218120254.png]]
**Adding a Decoy Duck**
![[Pasted image 20220218120329.png]]
![[Pasted image 20220218120426.png]]

**Limitations of inheritance** 
An Interface 
![[Pasted image 20220218120517.png]]
![[Pasted image 20220218120716.png]]

**Problems**
![[Pasted image 20220218120803.png]]
**Review**
![[Pasted image 20220218120841.png]]
![[Pasted image 20220218120940.png]]

## Encapsulate What Varies 
![[Pasted image 20220218121030.png]]

How to separate what varies with the ducks 
**Programming to an Interface**
![[Pasted image 20220218121203.png]]
This is an has a relationship 
- A duck has a quack behavior and a has a fly behavior 
![[Pasted image 20220218121222.png]]
![[Pasted image 20220218121410.png]]

## Encapsulate what varies Code Example
![[Pasted image 20220218121732.png]]
![[Pasted image 20220218121746.png]]
**Abstract  classes have to implement the abstract method**
Fly behavior and quack behavior will be used to compose a duck using the interface types for these variables, Will be able to store any behaviors in these behaviors.

![[Pasted image 20220218121920.png]]
Initialize the behavior with a default constructor

![[Pasted image 20220218122117.png]]
![[Pasted image 20220218122229.png]]
![[Pasted image 20220218122426.png]]

**The Strategy Pattern**
Defines a family of algorithms, encapsulates each one making them interchangeable. Lets algorithms vary independently from one another.  

![[Pasted image 20220218122657.png]]

## Why has-a is better than is-a
Is-a - inheritance 
has-a = composition behavior 
![[Pasted image 20220218124243.png]]
![[Pasted image 20220218124257.png]]

**Comparison**
![[Pasted image 20220218124317.png]]
![[Pasted image 20220218124323.png]]

# Adapter Pattern
## Overview 

![[Pasted image 20220218130244.png]]
- Allows us to translate requests from one class to another
![[Pasted image 20220218130317.png]]
![[Pasted image 20220218130351.png]]
![[Pasted image 20220218130549.png]]

## Code Example
![[Pasted image 20220218130654.png]]

**Initial Problem**
Implementing a turkey into the the duck simulator 
![[Pasted image 20220218130755.png]]
![[Pasted image 20220218130833.png]]

![[Pasted image 20220218131042.png]]
**Implements the duck interface**
The duck methods delegated to the turkey methods 
Turkeys don't fly as well as ducks so it's called 5 Times
****
![[Pasted image 20220218131250.png]]

![[Pasted image 20220218131420.png]]

****

# Observer Pattern
## Overview 
Keep designs more flexible and minimize the complexity when different objects need to be kept up to date.
![[Pasted image 20220218132023.png]]

**Publisher and Subscribers**

![[Pasted image 20220218132447.png]]
![[Pasted image 20220218132402.png]]

**Definition**
![[Pasted image 20220218132534.png]]

1 to many relationships 
![[Pasted image 20220218132618.png]]
They are dependent on the subject for data
Helps clean up data 

**UML Example**
![[Pasted image 20220218132723.png]]
## Code Example 
![[Pasted image 20220218132808.png]]

****
![[Pasted image 20220218132829.png]]

**Simple subject manages the list of observers**
![[Pasted image 20220218132933.png]]
![[Pasted image 20220218132948.png]]

![[Pasted image 20220218133014.png]]
![[Pasted image 20220218133028.png]]
![[Pasted image 20220218133046.png]]

## Loose Coupling
![[Pasted image 20220218133156.png]]
Any class can subscribe 

This is all the Subject knows:
![[Pasted image 20220218133253.png]]

- Any changes made from observer or subject do not affect others allowing for cleaner code and debugging.

# Decorator Pattern
## Overview
**Coffee Shop order system**
![[Pasted image 20220218173739.png]]

- Future improvements are when customers want to extend customize their orders and make custom drinks
![[Pasted image 20220218173841.png]]

New design 
![[Pasted image 20220218173944.png]]
- Example order 
![[Pasted image 20220218174001.png]]
![[Pasted image 20220218174010.png]]

- Price changes to cause a high degree of maintenance
****
**The solution to Coffee Shop System**

**Open-Closed Principle**
![[Pasted image 20220218174750.png]]
![[Pasted image 20220218174844.png]]

Using what we learned from past patterns 
![[Pasted image 20220218175034.png]]

UML Example 



![[Pasted image 20220218175429.png]]
![[Pasted image 20220218175537.png]]
**Explanation**
When each decorator is wrapped it allows the same methods to be called continuously allowing each objects to calculate its own cost.


![[Pasted image 20220218175146.png]]
- Objects become composed and are responsible for their own cost 
![[Pasted image 20220218175243.png]]
![[Pasted image 20220218175300.png]]

**Definition of the decorator pattern**
![[Pasted image 20220218175323.png]]
## Using the Decorator Pattern 
**Starbuzz Coffee example**
![[Pasted image 20220218175806.png]]
![[Pasted image 20220218175815.png]]

**Concrete Components**
![[Pasted image 20220218175847.png]]

**Decorators**
![[Pasted image 20220218175924.png]]

**Condiment Decorator**
![[Pasted image 20220218175957.png]]
- We add on to the initial beverage 

**Construction**
![[Pasted image 20220218180221.png]]
- We store it as a beverage so we can keep adding to the cost using the same methods.



# Iterator Pattern
## Overview 
Most modern languages allow you to store a objects 
Allows you to iterate over Different storage types such as arrays and array lists 

**Definition**
![[Pasted image 20220218181614.png]]

**What is an aggregate object**?
![[Pasted image 20220218181656.png]]
![[Pasted image 20220218181739.png]]
Go through objects without needing to know the individual ways 
## Using the iterator pattern
![[Pasted image 20220218181839.png]]
The aggregate object is a menu 
![[Pasted image 20220218181929.png]]
Both the pancake house and the café can use the same interface to go through the same menu 

**Iteration Responsibilities**
The café is responsible for going through both menu's currently but using the iterator we can de-couple this responsibility to the iterator interface
![[Pasted image 20220218182142.png]]

![[Pasted image 20220218182203.png]]
![[Pasted image 20220218182213.png]]

**Improvement**
![[Pasted image 20220218182250.png]]



## Using built-in iterators
![[Pasted image 20220218182404.png]]
![[Pasted image 20220218182438.png]]

## Single Responsibility Principle
## More Built in iterators 

![[Pasted image 20220218182529.png]]
![[Pasted image 20220218182626.png]]
![[Pasted image 20220218182718.png]]

**Java**
![[Pasted image 20220218182745.png]]

**Python**
![[Pasted image 20220218182758.png]]

**JavaScript**
![[Pasted image 20220218182816.png]]

****
**More**
![[Pasted image 20220218182831.png]]


# Factory Pattern
## Overview
![[Pasted image 20220218183222.png]]

**Example**
![[Pasted image 20220218183238.png]]
Using new locks us in implementation

**Initial Problem this pattern solves**
![[Pasted image 20220218183446.png]]
![[Pasted image 20220218183453.png]]
The pizza types get in the way of the open-close principle

****
**Solution**
![[Pasted image 20220218183543.png]]
Factory Example
![[Pasted image 20220218183606.png]]
![[Pasted image 20220218183623.png]]

**The Simple Factory Pattern**
![[Pasted image 20220218183706.png]]

![[Pasted image 20220218183724.png]]



## The Method Factory Pattern
2 different stores example 
![[Pasted image 20220220144413.png]]
Challenges :
 code duplication
![[Pasted image 20220220144455.png]]
## Factory method pattern 
![[Pasted image 20220220144707.png]]
![[Pasted image 20220220144716.png]]

Differ instantiation to the individual pizza classes
![[Pasted image 20220220144811.png]]

**Using the factory method pattern**
![[Pasted image 20220220145012.png]]
![[Pasted image 20220220145142.png]]
The subclasses decide on what pizza to make
![[Pasted image 20220220145153.png]]
![[Pasted image 20220220145212.png]]
# Challenge 
## Strategy Pattern
![[Pasted image 20220218124431.png]]
- Add another way to share, separate the sharing method
- ![[Pasted image 20220218124600.png]]
**Solution**
![[Pasted image 20220218124844.png]]

## Adapter Pattern
![[Pasted image 20220218131617.png]]
Use the drone interface to in the duck simulator so the duck uses the drone interface.
### Solution 
![[Pasted image 20220218131737.png]]



## Observer Pattern
![[Pasted image 20220218133433.png]]

The subjects are interested in the data the weather station has 
### Solution
![[Pasted image 20220218133537.png]]
- A new subject interface was created that the weather station implements 
- A list of observers was added to the weather station 
- A method that allows the observers to come and go 
- notify observers when the data changes 
- A new observer interface has been added to update the subscribers when the weather changes
- Each class  has a reference to the weather station to add and remove themselves. 
## Decorator Pattern
**Pizza Store system**
![[Pasted image 20220218180349.png]]
Design a decorator for the pizza store 
![[Pasted image 20220218180418.png]]

- Topping Inherits from the pizza and uses an abstract get Description 
- Allowing the other topping to add on  the topping Decorator 
- Inheritance to get a super type of pizza and then use compassion to create the Topping decorator. 

## Iterator Pattern
- Learn how each language uses the iterator pattern 
![[Pasted image 20220218182927.png]]

**Solution**

**Swift  example**
![[Pasted image 20220218183009.png]]

## Factory Pattern
![[Pasted image 20220220145333.png]]

# Books
- Head First Design Patterns
