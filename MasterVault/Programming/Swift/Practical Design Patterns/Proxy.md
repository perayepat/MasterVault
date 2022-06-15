# Overview
![[Pasted image 20220615063142.png]]

**Uses**

- You have a resource hub where you want the user to access the surrogate first
- You relay on a web service where the remote proxy acts as local placeholder to control and access data from the real resource. (Commonly used in APIs)
- You use protective or sensitive resources, expose methods to query users for the access state. 
![[Pasted image 20220615063555.png]]

![[Pasted image 20220615063609.png]]


# Code 
``` Swift 
import Foundation

class RandomIntWithID {
    
    //computed property using a closure
    var value: Int = {
        print("value initialized")
        return Int.random(in: Int.min...Int.max)
    }()
    
    //this will only be initiialised when we access it
    //This is not thread safe and when multiple instance try to access it at the same time that will cause errors
    lazy var uid: String = {
        print("uid initialized")
        return UUID().uuidString
    }()
}

let n = RandomIntWithID()
print(n.uid)

```