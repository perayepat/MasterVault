# Overview 
Popular for passing a request where you have objects organized in a sequence.

![[Pasted image 20220615064119.png]]

the receivers form a chain and the request travels down the chain.  and if the object that has the current request isn't interested it is then forwarded down the chain. The request travels down until one of the object's is interested in the request.

**Implementation**
Implemented in the form of a singly linked list, with each receiver holding a reference to its successor in the chain. 

![[Pasted image 20220615064252.png]]

the end of the chain is null or a special method is called 
![[Pasted image 20220615064558.png]]


In some cases the responder forwards the request in the chain after its handled. This is how ios handles click and is commonly used in `Cocoa touch `
![[Pasted image 20220615064739.png]]


![[Pasted image 20220615064936.png]]


# Code 
``` Swift 
import Foundation

/// all  request handlers will need to adopt this
protocol RequestHandling {
    // oprional so callers can mark the end of the chain
    init(next: RequestHandling?)
    func handle(request: Any)
}

///created as final to prevent the createion of subclasses
///created with a type parameter to handle different tyoes of data
///adding a custom discription by adding a `CustomStringConvertible`
final class Handler<T>: RequestHandling, CustomStringConvertible {
    //if its nil then we've hit the end of the chain
    private var nextHandler: RequestHandling?
    
    init(next: RequestHandling?) {
        self.nextHandler = next
    }
    
    func handle(request: Any) {
        ///check if the request type is a type that can be handled
        if request is T {
            print("Request processed by \(self)")
        } else {
            /// check if theres a next handler in the chain if not print and return
            guard let handler = nextHandler else {
                print("Reached the end of the responder chain")
                return
            }
            ///if there is a valid method
            handler.handle(request: request)
            print("\(self) can't handle \(T.self) requests - forwarding to \(handler)")
        }
    }
    ///the description describes what request typ is procced by the given handler
    public var description: String {
        return "\(T.self) Handler"
    }
}

/// we start from the last to first
let dataHandler = Handler<Data>(next: nil)
let stringHandler = Handler<String>(next: dataHandler)
let dateHandler = Handler<Date>(next: stringHandler)

let data = Data(repeating: 0, count: 10)
dateHandler.handle(request: data)

//dateHandler.handle(request: 42)

```