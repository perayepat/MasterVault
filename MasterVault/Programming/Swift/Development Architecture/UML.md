# Overview 
 UML ( Unified Modelling Language )

These help us create the blueprint of all the uses a user could be using


**The use case Diagram** 

this shows the system from the users point of view 
![[Pasted image 20220622070649.png]]


**The Class Diagram**

These help us describe a structure of a software system by looking at classes attributes and the relations between them.  

![[Pasted image 20220622070816.png]]


**The Sequence Diagram**

![[Pasted image 20220622071047.png]]



# Use case Diagram 
The use cases in the diagram show us what the system is capable of. 
This is a straight forward way to describe the functionality of a system. 
![[Pasted image 20220622071246.png]]
the absence of a use case means the system isn't capable of that feature 

# Class Diagram 
Shows the entities that form our system and the relation between them. 
Minus is private 
Plus is public 
Hash mark denotes protected visibility 

![[Pasted image 20220622071559.png]]

**Inheritance**
The hollowed triangle points the the super class. 
![[Pasted image 20220622071816.png]]

**Association**
This tells us that a class knows about another class denotes by the solid line 

![[Pasted image 20220622071936.png]]

**Directed Association**
this tells us once class knows about the other class , but not the other way around 

![[Pasted image 20220622072104.png]]

**Dependency**
An example of this is when one class receives a reference of another class 
shown as a dashed arrow starting from the dependent class pointing to the class it depends on. 
![[Pasted image 20220622072212.png]]

**Aggregation**
a special form of association where one object has its own aggregated life cycle but it can't belong to another. 
However if the university closes down the student is no longer a associated with it. 
![[Pasted image 20220622072532.png]]


**Composition**
This is a stronger form of aggregation, which also implies ownership which means the parts die with the whole. 

![[Pasted image 20220622072752.png]]

**Composition Directed**
![[Pasted image 20220622072810.png]]

**Interface Realization**
when a type implements a abstract definition like swift protocols 
![[Pasted image 20220622072902.png]]


# Sequence Diagram 
When we need to express how objects interact with each other, describes a specific feature of the diagram. 

**Objects in a sequence diagram**
the line represents the life line of the object 
![[Pasted image 20220622073032.png]]

**Create messages**
these point to the object that's created 

![[Pasted image 20220622073150.png]]

**Ordinary Message**
shown as arrows that point to the receiver which will execute the method call. 
![[Pasted image 20220622073330.png]]

**Example**

- The login controller view creates the secure storage object 
- then retrieves the credentials like user name and password
- A communicator is then created 
- the 

![[Pasted image 20220622073351.png]]
![[Pasted image 20220622073554.png]]
