# Overview 
Uses :
- You need to create multiple versions of a large file , and that file needs to open and store something in memory. 
- The prototype pattern solves this by copying and instance instead or creating a new from sctatch all the time. 

![[Pasted image 20220608071625.png]]
*Img 1*

![[Pasted image 20220608071743.png]]

# Code 
![[Pasted image 20220608073209.png]]

**Explination**
The two instances are different and changing the clone didn't effect the origional 

Whenever you assign  object value type to another object its value gets copied and then used to initialize the clone.

If thee object is of a value type we get the cloning behavior for free. 

Structs allow for copying and this cloning behaviour while classes are refrence types. 

# Pitfalls of cloning refence Types

![[Pasted image 20220608074559.png]]
 **Explination**

when using a class the two objects share the same slot in memory changing one changes the other.  We have two refrences for the same instance. 

## Cloning Refrence Types
![[Pasted image 20220608075237.png]]
When cloning refrence types using the `NSCopying` is needed to create a new clone

![[Pasted image 20220608075405.png]]
Changing the clone doesn't effect the origional object as they point to different slots in memory . 

`.Copy()` 
- needed when cloning refrence typse and you also need to cast it as the type your cloning as it does chose any by default. 

**A more elegant solution**
![[Pasted image 20220608075854.png]]


![[Pasted image 20220608075903.png]]

# Code
``` Swift
import UIKit
import Foundation


struct NameStruct {
    
    var firstName: String
    var lastName: String
    
}

var joe = NameStruct(firstName: "joe", lastName: "Sat")
var pat = joe

print("\(joe), \(pat)")

pat.firstName = "Pat"
pat.lastName = "Mack"

print(" \n\n \(joe), \(pat)")

```
