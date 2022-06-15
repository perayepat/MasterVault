# Overview


![[Pasted image 20220608080508.png]]

This is a creational pattern that promotes lose coupling , so the callers dont need to know the implimentation types just he protocol and the base class 

![[Pasted image 20220608080932.png]]

Since only the methods and the protocols are exposed to the callers this allows us to pefrom changes without having to refactoter the depending components. We can even add new implimentation types without effecting the callers.

![[Pasted image 20220608081033.png]]

![[Pasted image 20220608081356.png]]

Only enforce the same protocols on classes or structs that are related not ones that peform different tasks 

# Code
Were able to use the methods from each of these classes needing any other extra work
``` Swift
import Foundation

protocol Serializable{
    func serialize()
}

class JSONSerializer: Serializable{
    func serialize() {
        print("JSONSerializer \(#function)")
    }
}

class PropertyListSerializer: Serializable{
    func serialize() {
        print("PropertyListSerializer \(#function)")
    }
}

class XMLSerializer: Serializable{
    func serialize() {
        print("XMLSerializer \(#function)")
    }
}

enum Serualizers {
    case json
    case plist
    case xml
}

func MakeSerializer(_ type: Serualizers) -> Serializable? {
    let result: Serializable?
    switch type{
    case .json: result = JSONSerializer()
    case.plist: result = PropertyListSerializer()
    case.xml : result = XMLSerializer()
    }
    
    return result
}

// Using a struct
struct SerializerFactory{
   static func MakeSerializer(_ type: Serualizers) -> Serializable? {
        let result: Serializable?
        switch type{
        case .json: result = JSONSerializer()
        case.plist: result = PropertyListSerializer()
        case.xml : result = XMLSerializer()
        }
        
        return result
    }
}


// acting as the caller

let jsonSerializer = MakeSerializer(.json)

//in use
jsonSerializer?.serialize()

//Struct one
let pList = SerializerFactory.MakeSerializer(.plist)
pList?.serialize()

```

