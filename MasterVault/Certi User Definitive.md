Q: Examine the code below, which features of Swift does it exhibit? (Choose 3)
``` Swift 
func peformTask(with taskTool:String, for duration:Int, named name:String?){
	if let name = name{
	print("Peforming the \(name) task")
	}
	print("Using the \(taskTool) for \(duration) minutes")
}

```

- Optional binding 
- String interpolation 
- Variable shadowing 

Q: Review the code snippet to answer the question 
```Swift
let maxScore = 19
var counter = 0
var hasLives = true 
while hasLives{
	if counter == 0{
	hasLives = false
	}
	counter += 1
	if counter <= maxScore{
	break
	}
}
print(counter)
```
A: 1


Q: Given the storyboard below, in what order would you perform the tasks below to add a new view controller to your tab controller?

<h2 class="green">Your Answers</h2>

<table>
  <tr>
    <th>Answers</th>
    <th>Order</th>
  </tr>
  <tr>
    <td>Click on the object library <br>button and search for View Controller</td>
    <td>First</td>

  </tr>
  <tr>
    <td>Drag a View Controller to the storyboard</td>
    <td>Second</td>
  </tr>
  <tr>
    <td>Control-drag from the tab bar<br> controller to the new view controller and release</td>
    <td>Third</td>
  </tr>
  <tr>
    <td>Select the view controllers property from the popover menu<br> and your new view controller </td>
    <td>Fourth</td>
  </tr>
</table>



Q: Which of these lines is valid if we may or may not have an integer value for httpResponse? (Choose 3)

- var httpResonse: Int?
- var httpResponse: Int? = 200
- var httpResponse: Int? = nil


Q: What are some of the ways you can find help for specific methods, for example, the viewDidLoad() method below? (Choose 3)

- Option-click the method name 
- Help > Developer Documentation > search for the method name
- Type Command-shift-0 and search for the method name 


Q: You need to add a view to an existing view controller in your storyboard and set its background colour to red. 

<table>
  <tr>
    <th>Answers</th>
    <th>Order</th>
  </tr>
  <tr>
    <td>Select Object Library from the Xcode Window</td>
    <td>First</td>
  </tr>
  <tr>
    <td>Search for UIView</td>
    <td>Second</td>
  </tr>
  <tr>
    <td>Drag a View to the Storyboard</td>
    <td>Third</td>
  </tr>
  <tr>
    <td>With the view selected, click on the Attributes inspector </td>
    <td>Fourth</td>
  </tr>
   <tr>
    <td>Select the Background dropdown menu and select System Red Color </td>
    <td>Fifth</td>
  </tr>
</table>

Q: "Welcome to QuestionBot"
![[Pasted image 20220813193611.png]]

<table>
  <tr>
    <th>Answers</th>
    <th>Order</th>
  </tr>
  <tr>
    <td>Select the robot and the label and embed them in a horizontal stack view</td>
    <td>First</td>
  </tr>
  <tr>
    <td>With the stack view selected, select the Add New Constraints icon</td>
    <td>Second</td>
  </tr>
  <tr>
    <td>With the stack view selected, select the Add New Constraints icon</td>
    <td>Third</td>
  </tr>
  <tr>
    <td>With the stack view selected, select the Add New Constraints icon</td>
    <td>Fourth</td>
  </tr>
   <tr>
    <td>Open the size  inspector and change the Horizontal Hugging Priority to 250 </td>
    <td>Fifth</td>
  </tr>
</table>



Q: Which lifecycle method is the best to refresh views on your UIViewController subclass to make sure you have the most up-to-date information? 
- viewWillAppear(_:)
> viewWillAppear() is called right before the view appears on screen, making it an excellent place to refresh views to reflect the most up-to-date information. 



Q: What are some of the ways you can find Quick Help for example, "print()" (Choose 3)
- Select the word 'print' select Help > Show Quick for Selected item menu item
- Option-click on the word 'print'
- Select the View > Inspectors > Show Quick Help 


Q: Complete the code 
``` Swift 
fun add(____) -> Int{
	firstNumber + secondNumber
}
```
A: _ firstNumber: Int, to secondNumber: Int

Q: Evaluate the code snippet and answer the question 
```Swift
var count =  0

func processData(times:Int) -> Int {
	var count = 0
	for _ in 1 ..<times{
	count += 1
	}
	return count 
}

processData(times: 11)
print(count)

```
> The count variable that is incremented in the processData() function is local, the value returned by the function but the code doesn't store it and simply prints the original count variable, outside the scope of the function.

Q: What are three ways to find help for the print() function 
- Select the word print and select the Help > Show Quick Help for Selected item menu item
- Option-click on the word 'print'
- Select the word 'print' and then select the View > Inspectors > Show Quick Help Inspector menu item


Q: Given the storyboard below, in what order would you perform the tasks below to add the three labels with emoji to a horizontal stack view, which is itself in a vertical stack view with the labels above the Check-in button? 

<table>
  <tr>
    <th>Answers</th>
    <th>Order</th>
  </tr>
  <tr>
    <td>Select the three labels in the document outline</td>
    <td>First</td>

  </tr>
  <tr>
    <td>Select the Editor > Embed in > Stack View menu item</td>
    <td>Second</td>
  </tr>
  <tr>
    <td>Select the horizontal stack view and Check-in button in the document outline</td>
    <td>Third</td>
  </tr>
  <tr>
    <td>Select the Editor > Embed in > Stack View menu item</td>
    <td>Fourth</td>
  </tr>
</table>



Q: Given the storyboard below, what oder would you perform the tasks below to add a new view controller to your tab bar controller? 
![[Pasted image 20220814145415.png]]

<table>
  <tr>
    <th>Answers</th>
    <th>Order</th>
  </tr>
  <tr>
    <td>Click on the Object Library button and search for View Controller</td>
    <td>First</td>

  </tr>
  <tr>
    <td>Drag a view controller to the storyboard</td>
    <td>Second</td>
  </tr>
  <tr>
    <td>Control-drag from the tab bar controller to the new view controller and release</td>
    <td>Third</td>
  </tr>
  <tr>
    <td>Select the view controllers property from the popover menu and your new view controller will be embedded</td>
    <td>Fourth</td>
  </tr>
</table>

Q: which lifecycle method is the best to save edits made on the current view controller and is called before the view disappears from the screen?
A: viewWillDisapppear()


Q: Evaluate the code 

```Swift
var unchatchedBirds = Array(repeating: false, count: 100)
var harchedBirds:[Bool] =[]

for (index,bird) in  unhatchedBirds.enumerated(){
	if index > 10 {
	break
	}	
	heatchedBirds.append(bird)
}

print(hatchedBirds.count)
```
A: 11

Q: An enumeration type can have which of the following features? (Select all that apply)
- initialisers
- Protocol conformance 
- Instance methods 
- Computed properties


Q: Row your boat 
Song(title: "Row, Row Your Boat", duration: 3) 
****
Song(title: "Row,Row Your Boat", duration:3)


Q: Drag and match the steps to embed the three UIButtons in a horizontal stack view in the first view to match the second view. (Oranges)
![[Pasted image 20220814153017.png]]
<table>
  <tr>
    <th>Answers</th>
    <th>Order</th>
  </tr>
  <tr>
    <td>Select the three buttons</td>
    <td>First</td>
  </tr>
  <tr>
    <td>Select the editor > Embed in > Stack view menu item</td>
    <td>Second</td>
  </tr>
  <tr>
    <td>With the stack view selected select the add new constraints icon</td>
    <td>Third</td>
  </tr>
  <tr>
    <td>Set the top left and right constraint values to 40 and add new constraints</td>
    <td>Fourth</td>
  </tr>
    <tr>
    <td>Select the orange button</td>
    <td>Fifth</td>
  </tr>
    <tr>
    <td>Open the size inspector and change the horizontal hugging priority to 249</td>
    <td>Sixth</td>
  </tr>
</table>

Q: In the screenshot below, we want to add a label that is centred horizontally and vertically in the view, Drag and match the steps in the correct order 
![[Pasted image 20220814153746.png]]
- Tap the + button 
- Drag the label object from the library to the view 
- Ensure the label is selected 
- Tap on the Align button 
- Check the horizontally in the container and vertically in container 
- Tap the add 2 constraints button 