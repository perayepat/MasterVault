# Overview
All objects in swiftui are structs 
- structs make their own implicit initializers 
- structs are value types made up of their values 
- Closures are functions passed as parameters 

**turnery if else then**
![[Pasted image 20220413132706.png]]

``` swiftUI
//short version of the if satement 

Text(pizzas > 5 ? "Hello Pizza!!!" : "Helllo World")
```
- in the text :
	  hello Pizza is when the condition is true 
	  Hello world is the else when the condition is false 


**Viewing Multiple devices**
![[Pasted image 20220413134512.png]]
**Code:**

```swiftUI
	Group{
	ContentView()
	ContentView()
		.colorScheme(.dark)
		.background(Color.black)
		.previewDevice("iPad Pro (9.7-inch)") /
	}
	//setting the preview device changes the second content view to the 
	  iPad
````