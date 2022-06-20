# Overview 

when using a for loop or traversing through a list of data your relying on the iterator pattern. The internal structure isn't exposed. 

![[Pasted image 20220615070240.png]]

Iterating through the elements of a custom linked list or a stack, 
![[Pasted image 20220615070346.png]]

![[Pasted image 20220615070521.png]]
![[Pasted image 20220615070609.png]]


# Custom Queue and Custom Iterator 
``` Swift
// Custom queue implementation

private final class Node<T> {
    var key: T? //stores anytype
    var next: Node? //Sets the next node , optional because the next node can be nil
    
    //sets the property
    init(_ value: T? = nil) {
        key = value
    }
}

final class Queue<T> {
    fileprivate var head: Node<T>?
    private var tail: Node<T>?
    
    func enqueue(_ value: T) {
        let newNode = Node<T>(value)
        // First element's value has not been set?
        guard head != nil else {
            head = newNode
            tail = head
            return
        }

        // append new element
        //by setting the tail refrence to the new node
        tail?.next = newNode
        tail = newNode
    }
    
    // Dequeue returns the top the level item to the queue uses FIFO
    func dequeue() -> T? {
        guard let headItem = head?.key else {
            return nil
        }
        //check for a valid next node
        if let nextNode = head?.next {
            head = nextNode
        } else {
            //when the head is the only valid item
            head = nil
            tail = nil
        }
        return headItem
    }
    
    func isEmpty() -> Bool {
        return head == nil
    }
    // Getting the top item without taking it out
    func peek() -> T? {
        return head?.key
    }
}

//MARK: Handles making the iterator protocol work when creating a custom queue
struct QueueIterator<T>: IteratorProtocol{
    private let queue: Queue<T>
    private var currentNode: Node<T>?
    
    init(_ queue: Queue<T>) {
        self.queue = queue
        currentNode = queue.head
    }
    
    //implement the next method to adopt the iterator protocol
   mutating func next() -> T? {
       //check if the current node isnt nil
        guard let node = currentNode else {
            return nil
        }
        
        let nexKey = currentNode?.key
        currentNode = node.next
        return nexKey
    }
}
extension Queue: Sequence{
    func makeIterator() -> QueueIterator<T> {
        return QueueIterator(self)
    }
}


var queue = Queue<Int>()
queue.enqueue(1)
queue.enqueue(2)

for item in queue {
print(item)
}

```