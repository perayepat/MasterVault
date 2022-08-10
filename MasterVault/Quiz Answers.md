**Q:** Which two ways of the following statements are valid ways to call this function.

	![[Pasted image 20220808163651.png]]


**Q:** Which feature is available for stored properties, but not computed properties ? 
	**A: Type Inference**
	> Computed properties must explicitly declare their type. Stored properties can let the compiler infer their type. 

**Q:** What keyword is used in the declaration of functions and methods but not initializers
	**A: func**


**Q:** How should you fix the error in the following code snippet
	**A: Assign local variable name into self.name**
	![[Pasted image 20220808164611.png]]

**Q:** Which line of code needs to change to allow the code snippet to compile
	**A: class Chow {**
	> there is an inheritance problem, the code line class "Cow" calls super init but super.init does not have a superclass declared

**Q:** Which type should you use for userName so that the code will compile 
	**A: String!**
	> String ? can be set to nil but it cannot be used as `userName.count` without being unwrapped.

**Q:** An initializer that might return ___ is called a failable initializer  
	 **A: Nil**

**Q:** why will this code snippet fail to compile (Dictionary Question)
	**A: Dictionary subscripting returns an optional value**
	![[Pasted image 20220808165755.png]]


**Q:** what is the effect of the expression shape `["depth"]` int this snippet 
	**A: It will return nil**
	> the shape dictionary doesn't have a depth key and will return nil.
	

**Q:** which cast should you place in the blank to complete the code snippet? 
	**A: as?**
	![[Pasted image 20220808170516.png]]

**Q:** Which type defines an array that has no restrictions on the types of its contents? 
	**A : [Any]**

**Q:** Which keyword, if used in the blank above would cause the loop to end the current iteration prematurely and move on to the next iteration ?
	**A : Continue**

**Q:** Which response should you use to complete this code snippet ?
	**A : guard**
	> "let" is used to assign a value to a constant, The expression is checking the condition not assigning a value 

**Q:** What are two places you should use a guard statement 
	**A : 
	- To unwrap Optionals without creating a nested scope
	- to return early from a function if certain conditions are not met**

**Q:** Match the higher order function in Column A by dragging to Column B (filter)
	![[Pasted image 20220808172056.png]]

**Q:** What is an important consideration regarding closures and memory management ?
	**A: Closures can prevent deallocation of objects from their enclosing scope**

**Q:** When writing a closure, what is the role of the `in` Keyword ? 
	**A: it separates the closure's signature from its body**
	> A closure can operate in many types of values not only collections 

**Q:** Match Column A to  Column B (Array methods) 
	![[Pasted image 20220808173320.png]]

**Q:** Which protocol does Comparable inherit requirements from ?
	**A: Equitable**


**Q:** Why will this code fail to compile ? (if let)
	**A: The else syntax in this snippet is for a guard let statement, not an if let statement**
	![[Pasted image 20220810084237.png]]
	

**Q:** What should the badge value be set to if you want to clear a tab bar item's badge ?
	**A: nil**

**Q:** The view controller appearance callbacks each take an argument of type.
	**A: - Bool 
		- Animated**

**Q:** which application delegate callback notifies your app of an interruption such as an incoming phone call ? 
	**A: `applicationWillResignActive()`**
	