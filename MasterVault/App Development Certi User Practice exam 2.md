**Q:** Review the code below and choose the keyword or keywords that are missing (guard let)
![[Pasted image 20220811181518.png]]
	**A: guard let**
	> if we use guard let it will make the username constant available throughout the function so we can use it to perform our login logic below 

**Q:** What value will print to the console at the end? (number one)
![[Pasted image 20220811181742.png]]
	**A:** 0
	> the count variable that is incremented in the processData(times:) function is local, the value is returned by the function but the code doesn't store it and simply prints the original count variable.
	
**Q:** For the following code, what will the result value and type be? 
	![[Pasted image 20220811182016.png]]
	**A:** 15.0 , double 

**Q:** what will be printed to the console when we run the following code? (handleResponse)
![[Pasted image 20220811182156.png]]
**A:** a runtime error 
> when you force-unwrap a value that was nil, it will cause a crash in our app at runtime

**Q:** How many times does the value "Hello" appear in the hellos array after running the code?
	![[Pasted image 20220811182337.png]]
	**A:** 97 
	> We start out with 100 instances of "Hello" in the array and remove the "Hello" at index 55 then remove the last "Hello" in the array.
	> the item at index 55 is then replaced by the word "World", so in all 3 instances of the string "Hello" have been removed or replaced.
	
**Q:** Review the code snippet, What are the valid ways to call this function? (Choose 3)
	![[Pasted image 20220811182650.png]]
	> The function requires that we provide the parameters syrup and iceCreamFlavor, so every call to the function must include those parameters. 
	> If we don't want to provide a value for syrup we can use nil for the parameter value.
	> Because the fruit parameter has a default value we can safely omit that parameter in our function call 
	
**Q:** How could you declare a property mySign that has a value of the rock case of a Sign enum type? (Choose 3)
	![[Pasted image 20220811183125.png]]
	> To allow Swift to infer the storage for our mySign constant we need to give enough information to know what type we will be storing.
	
**Q:** What code would we write to use the Distance type's conversion from centimetres to inches?
	![[Pasted image 20220811183454.png]]
	> distance.inches
	> The inches computed property is defined on the Distance struct, which will convert the distance in centimetres we created to inches. You access computed properties like you do regular properties, with dot notation.
	
**Q:** When executing the code, the integer value printed is 
	![[Pasted image 20220811183812.png]]
	> Classes are reference types, so changing the properties of one will update the properties of a variable referring to the same instance.
	
**Q:** Given the following code, how could you write the parameters so that our function takes two parameters, both of type int? The function will be called without a first parameter label and with a second label of to.
	![[Pasted image 20220811184040.png]]
	>_ firstNumber: Int, to secondNumber: Int

_ secondNumber: Int, to firstNumber: Int

**Q:** Drag and match the code on the list area to the missing code in the sample below, the function should take an Int as a parameter and return an Int.
	![[Pasted image 20220811184358.png]]

**Q:** Drag the methods to the correct order. These methods are implemented on our initialViewController which will get loaded first and then the user taps away to our SecondViewController
	![[Pasted image 20220811184535.png]]
	> viewDIdLoad
	> viewWillAppear
	> viewDidDidAppear
	> viewWillDisappear
	> viewDidDisappear

**Q:** You are designing an app to catalog animals in your zoo. Your animal object will have the following properties:
	![[Pasted image 20220811184813.png]]
	> let = type 
	> var = weight
	> let = dateAcquired
	> var = lastFed
	
**Q:** Given the storyboard below, in what order would you perform the tasks below to add the three labels with emoji to a horizontal stack view, which is itself in a vertical stack view with the labels above the check in button?
	![[Pasted image 20220811185058.png]]
	> Selected the three labels in the document outline view 
	> Select the Editor > Embed in > Stack view menu item.
	> Select the horizontal stack view and check in button in the document outline 
	> Select the Editor > Embed in > Stack View menu Item
	
**Q:** in the scene below we want to embed our two view controllers in a tab bar controller, the tab with the fruit emoji should be labeled "Food" and should have a star icon in the tab bar.
	![[Pasted image 20220811185410.png]]
	> Command select each View Controller in the document outline 
	> Select the Editor > Embed in > Tab Bar Controller menu item 
	> Select the item in the document outline under the view controller containing the fruit emoji
	> In the Attribute inspector, change the title of the bar item to "Food" and change the image property in the Bar item section to "star.fill"
	

**Q:** We have a view controller displaying a list of emoji we can have translated into another language. An emoji is on a button, which is connected to the appleButtonPressed() @IBAction.
	![[Pasted image 20220811185846.png]]
	> loaded our food view controller 
	> the Apple button was pressed 
	> Showing the selected item
	> We have performed the segue 

**Q:** Which lifecycle method is the best to refresh the view on your UIViewController subclass to make sure you have the most up-to-date information, including reacting to possible screen orientation changes? 
	**A:**  viewWillAppear()

**Q:** What are some of the ways you can find Quick Help for specific code, 
	**A:**   - Option-click on the 
		- Select the View > Inspectors > Show Quick Help
		- Select the Help > Show Quick Help 
	

