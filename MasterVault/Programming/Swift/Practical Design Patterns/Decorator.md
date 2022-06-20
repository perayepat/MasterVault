# Overview
Adds new responsibility to objects dynaically, without modifying the code of the underlying types. 

![[Pasted image 20220609072034.png]]
![[Pasted image 20220609072050.png]]
![[Pasted image 20220609072127.png]]
![[Pasted image 20220609072141.png]]

## Decorator Class example
``` Swift
import Foundation

/// Decorating an object means you wont have to change other objects of the same type
/// Attach additional responsibilities to objects

//MARK: Object decorator
/// user defaults can't store and retrieve date instances and using the decorator pattern here were able to add that funcitonallity


///the decorator has to use the the inplimented interface
class UserDefaultsDecorator: UserDefaults{
    private var userDefualts = UserDefaults.standard
    
    /// can call this initializer and only enter one parameter,
    /// set the rest as defaults
    convenience init(userDefualts: UserDefaults){
        self.init()
        self.userDefualts = userDefualts
    }
    
    ///set date fot key
    func set(date: Date?, forKey key:String){
        //delagates to the userdefualts set
        userDefualts.set(date, forKey: key)
    }
    
    ///date for key
    func date(forKey key: String) -> Date {
        return userDefualts.value(forKey: key) as! Date
    }
}

//MARK: Using it like its a userdefaults Instance


let userDefualts  = UserDefaultsDecorator()

userDefualts.set(42, forKey: "Ans")
print(userDefualts.string(forKey: "Ans") ?? "?")

userDefualts.set(date: Date(), forKey: "now")


```

## Decorator Extension Example
Extensions can't override existing functionality and cant add stored properties or property observers to existing properties .

They can add new methods and computed properties

The new type functionality is now available to all the other instances of the type

``` Swift
extension UserDefaults {
///implement set date for key and date for key
///They will delgate the requests to the instances

    func set(date: Date?, forkey key: String){
        self.set(date: date, forkey: key)
    }
    
    //date for key
    func date(forKey key: String) -> Date? {
        return self.value(forKey: key) as? Date
    }
}

let userDefaults = UserDefaults.standard
userDefaults.set(Date(), forKey: "Now")
print(userDefaults.date(forKey: "Now") ?? "?")

```