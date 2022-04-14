# Overview 
Protocols are just another name for interfaces
![[Pasted image 20220406165902.png]]
![[Pasted image 20220406165920.png]]
![[Pasted image 20220406165946.png]]

**Protocol Orientated Approach**

- Start with a protocol before a class  
- Swift has built in support such as : 
	- extensions 
	- inheritance 
	- composition 
- Prefer value semantics over classes:
	- structs 
	- Enums 
	- tuples 
instead of exclusively with classes 


# Introduction 
**Protocol Naming**
![[Pasted image 20220406171533.png]]

![[Pasted image 20220406171600.png]]
![[Pasted image 20220406171550.png]] 


![[Pasted image 20220406171621.png]]
![[Pasted image 20220406171633.png]]

![[Pasted image 20220406173356.png]]
# Adopting Protocols
![[Pasted image 20220406174821.png]]


# Conforming to protocols via extensions
 
-using an encryption example 
**Applying it to the string type**

we can use type extension to add properties or methods to an existing type , even with no access to the source code 

![[Pasted image 20220406181354.png]]

# Understanding Polymorphism
**Polymorphism**

- area is the only conforming type the shapes must use 
![[Pasted image 20220406181942.png]]
notes
- shape , we can take advantage of polymorphism to adopt one of the concreate shapes 
- the same shape variable is being used

![[Pasted image 20220406182235.png]]
![[Pasted image 20220406182922.png]]

**Uses**
we can add any type that conforms to the shape protocol 
allows you to create the common functionality without knowing the actual type 
Useful for accessing common and related objects from a common interface without needing to know their concrete type 


# Protocol Inheritance 
a protocol can inherit from another protocol and this creates granular designs 
we are trying to follow the single responsibility system 

****
we will create a protocol for each set of requirements 
****
![[Pasted image 20220406190533.png]]
Tagged Persistable 
- adds a initializer that will identify the instance to be restored 
- function persist it takes the storage location
- throws are for variables that will throw errors 

**Notes**
Similar to class inheritance but not limited to one type of inheritance 
****
![[Pasted image 20220406190921.png]]

- **Taggable** - if it only needs to hold data that needs to be tagged 
- **TaggagedPersistable** - if it requires persistent capabilities 
- **Tagged Encodable** - retrieving the base 64 encoded string representation of the data 

# Protocol Composition 
![[Pasted image 20220406191354.png]]

![[Pasted image 20220406195115.png]]

# Protocol Extensions
Providing default behavior could save extra time when using protocols
![[Pasted image 20220406195905.png]]
**Notes**
by adding default behavior by means of extensions to the protocols conforming types don't need to implement the property extensions 
![[Pasted image 20220406195921.png]]
