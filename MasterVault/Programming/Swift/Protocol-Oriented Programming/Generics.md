# Overview 
generics save us from typing the same code over again 
Help cluttering code that defer by the type of their parameters 

![[Pasted image 20220621141518.png]]

**Problem**

you have a method that needs to calculate weather numbers are equal or not , but you have to check a range of data types to see weather they're equal or not. 


``` Swift 
func equals(lhs: Int, rhs: Int) -> Bool {
    // The iplementation is straightforward
    return lhs == rhs
}
```



**Solution**

To avoid creating all more equals functions for other data types you can use generics and group them all together 

``` Swift
    ///`Equatable` this protocol allows generic types to check weather they are equal or not
    /// `T: Equatable` this is a type constrait that tells the compiler that the method conforms to a certian type
    /// Now the function accepts instance that use the `Equatable` protocol, most data types use this protocol
func equals<T: Equatable>(lhs: T, rhs: T) -> String{
    if lhs == rhs {
        return "True"
    }
    else{
        return "False"
    }
}

equals(lhs: 1, rhs: 1)
```


# Working with generic types
**Overview**
 
Swift collection types are implemented as generic types 



**Code**

``` Swift 
struct StringWrapper {
    var storage: String
}

struct IntWrapper {
    var storage: Int
}

struct DateWrapper {
    var storage: Date
}

struct Wrapper<T: Equatable> {
    var storage: T
    init(_ value: T) {
        storage = value
    }
}

/*
 Using the generic version is straightforward
 */
let piWrapped = Wrapper<Double>(Double.pi)

/*
 In most cases, we can even skip the placeholder type.
 The compiler will figure out the type based on the arguments.
 Type inference works by examining the provided values while compiling the code.
 */
let piWrapped2 = Wrapper(Double.pi)

/*
 Now, let's create a new instance that wraps a String
 */
let stringWrapped = Wrapper("POP")

/*
 Or a Date wrapper
 */
let dateWrapped = Wrapper(Date())
```

# Placeholder types in protocols

**Overview**

this allows you to create a protocol that doesn't conform to any data type 
## Code 
`associatedtype` allows protocols to use place holders 
``` Swift 
import Foundation

protocol Taggable {
    ///`Associatedtype` this allows us to place and place holder type for the protocol
    ///the actual type is unkown until the conforming type provides it
    associatedtype Content
    
    
    var tag: String {get}
    var data: Content { get }
    init(tag: String, data: Content)
}

struct TaggedDouble: Taggable{
    
    var tag: String
    var data: Double
}


struct TaggedDate: Taggable{
    
    var tag: String
    var data: Date
}
```

# Using generics with protocols 
**Overview**

Generics allow protocol orientated programming to become fluid and flexible allowing you to create functionality faster

## Code
``` Swift 
import Foundation

protocol Taggable {
    ///`Associatedtype` this allows us to place and place holder type for the protocol
    ///the actual type is unkown until the conforming type provides it
    associatedtype Content : Equatable
    
    
    var tag: String {get}
    var data: Content { get }
    init(tag: String, data: Content)
}

struct TaggedDouble: Taggable{
    
    var tag: String
    var data: Double
}


struct TaggedDate: Taggable{
    
    var tag: String
    var data: Date
}

/// We'll  provide the type when we use the instace of this generic structures
struct GenericTagged<T : Equatable>: Taggable{
    var tag: String
    var data: T
}


let taggedDouble = GenericTagged(tag: "pi", data: Double.pi)

```

# Creating a generic stack 
![[Pasted image 20220621151602.png]]
![[Pasted image 20220621151627.png]]

## Code 
``` swift 
public protocol StackProtocol {
    associatedtype E
    
        //pushing elements into the stack
    mutating func push(_ item:E)
    
        // Removing the top element
    mutating func pop() -> E?
    
        //peek returns the top element
    func peek() -> E?
    
        //return the number of elements
    var count: Int{get}
    var isEmpty: Bool {get}
}

public struct Stack<T>: StackProtocol {
    private var storage = [T]()
    
    public mutating func push(_ item: T){
        storage.append(item)
    }
    
    public mutating func pop() -> T? {
        return storage.popLast()
    }
    
    public func peek() -> T? {
        return storage.last
    }
    public var count: Int{
        storage.count
    }
    
    public var isEmpty: Bool {
        storage.isEmpty
    }
}

var stringStack = Stack<String>()

StackProtocol.push("Hello")
StackProtocol.push("HI")
StackProtocol.push("Hell")

print(stringStack.pop() ?? "empty")
```
# Model-View-ViewModel

**Overview**

![[Pasted image 20220621181031.png]]
Separating the business logic and views using three components: 

**View**
Consists of all visual elements 
Concerned with tasks that are related to the view such as layout, color and animation. 

**View Model**
Represents the state of the UI

**Model**
The application state that handles and manages the logic of that's sent to the view. 

**Diagram**
The direction is a one way road where its loosely coupled and the ViewModel doesn't know about the view and the model doesn't know about the ViewModel.

Promotes stability and reusability  
![[Pasted image 20220621181538.png]]

The ViewModel propagates changes to the view using data bindings the view reacts to ViewModel changes, Using Swiftui and the Combine framework. 

**High level overview**

![[Pasted image 20220621182109.png]]
**View**
this allows the user to enter the name of the city and show the current weather in that city. 


![[Pasted image 20220621181954.png]]
**ViewModel**
  Using the observable object so were able to use data bindings. 

![[Pasted image 20220621182221.png]]
**Model**
This will provide weather information provided to us by the API. We encapsulate the initialization requests ,network requests and data conversions into dedicated controller types. 

Using protocols to decode the json information. 
![[Pasted image 20220621182453.png]]+