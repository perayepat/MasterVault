# Overview
## Forms 
Scrolling lists of static views such as images and text fields but they can also have more dynamic things like toggle views and switches.

``` Swift
// Forms can only take 10 items 
Form{
	Text("Hello World")
}
```
![[Pasted image 20220516094649.png]]


To split the items in a form you can use `Groups` or `Sections`, these allow you to have more than  10 items in a form. These are worked around the 10 Items restriction


![[Pasted image 20220516095022.png]]
``` Swift 
	Form{
		Group{
			  Text("Hello World")
			  Text("Hello World")
			  Text("Hello World")
		}
		Group{
				  Text("Hello World")
				  Text("Hello World")
				  Text("Hello World")
			}
		
	}
```
Groups look the same as a normal form and items aren't split up 


![[Pasted image 20220516095101.png]]
``` Swift 
	Form{
		Sections{
			  Text("Hello World")
			  Text("Hello World")
			  Text("Hello World")
		}
		Sections{
				  Text("Hello World")
				  Text("Hello World")
				  Text("Hello World")
			}
		
	}
```
Sections however will split the view up like the setting view in your iPhone 


## Navigation View
Used to navigate between views 

``` Swift
NavigationView{
	Form{
		Text("Hello World")
	}
	.navigationTitle("Title")
	//The navigation title goes inside the nav view not outside 

}
```

## Modifying program state
The active collection of changes and settings in programming is the state.
These describe how the UI looks at the current state

*E.g.  They can't do A until they complete B*

![[Pasted image 20220516101403.png]]
```  Swift 
struct ContentView: View {
 @State private var tapCount = 0
  NavigationView{
            Form{
                Button("Tap Count: \(tapCount)"){
                    tapCount += 1
                }
          }
     }
 
}
```
States allow you to update components in the view and SwiftUi will keep track of the changes

This is designed for simple use when update small items in the view

## Binding states to UI controls 
When you want to have a value you can get and set it in SwiftUI.
We use:
``` Swift 
@State var txtName = ""
```

when you want to set and get the `txtName` we use a `$` :
Without the `$` you are getting the value 


``` Swift 
struct ContentView: View {
 @State  var txtName = ""
    var body: some View {
    
    TextField("Enter Name", text: $txtName)
	Text("Your name is : \(txtName)")
	
    }
}


```
the $ sign tells swift we want to write to `txtName`

![[Pasted image 20220516102607.png]]


## Creating views in a loop
Foreach loops allow you to display and loop through a number of items and display them dynamically.

E.g. showing an array of :
	- Names
	- MenuItems 
	- Other Things

``` Swift
Form{
	 ForEach(0..<100){ number in 
	 Text("Row \(number)")
	 }
}

//Short Hand Version
Form{
	 ForEach(0..<100){ 
	 Text("Row \($0)")
	 }
}
```
This results in a form with 100 rows. 


**Picker View**
The `ForEach` is most useful with a picker view 

``` Swift 
struct ExampleCode: View {

  @State private var selectedStudent = "Harry
  let students = ["Harry", "Hermione", "Ron"]

	var body: some View{
	
	 Picker("Select your student" , 
	 selection: $selectedStudent){
		 ForEach(student, id: \.self){
			 Text($0)
			 }
		}
	}
}

```
`id: \.self`
	Swift needs to identify all the items in the array, Using self tells swift to use the items in the array as identifiers. 
	*This may be a problem when you have the same items in array. *

![[Pasted image 20220516142912.png]]

# App 

## Reading text from the user 
**Handling Integers using a text field**
![[Pasted image 20220516145837.png]]
``` Swift 
@State private var checkAmount = 0.0
TextField("Amount",value: $checkAmount, format: .currency(code: Locale.current.currentCode ?? "EUR") )
.KeyboardType(.decimalPad)
```

`Value` - allows you to set an int in the text field 
`Format` - Adds a currency pair to the int

`.currency(code: Locale.current.currencyCode ?? "EUR"))`
- This looks at the users region settings and sets it to the users current regional currency 
`.  .keyboardType(.decimalPad)` - Switches the normal keyboard to a keypad 

## Pickers in a form 
Pickers need a two way binding like `@State` to store and retrieve the values

`NavigationView` is needed when working with `Picker` as you need to go to a new view in order to make the selection to the picker. 
![[Pasted image 20220516151353.png]]


## Segmented Control
When using picker `.pickerStyle(.segmented)` allows you to show the picker in a different style

**Adding a header to the picker**
Adding a `header : {Text("Header")}`
allows you to add a header to the picker allowing the user to see what the picker can be used for 

![[Pasted image 20220516154108.png]]

## Calculating the total Per person
Using computed variables makes the calculation easier than using a method.

``` Swift
var totalPerPerson : Double{
//calculate the total per person

let peopleCount = Double(numberOfPeople + 2)
let tipSelection = Double(tipPercentage)

let tipValue = checkAmount / 100 * tipSelection
let grandTotal = checkAmount + tipValue
let amountPerPerson = grandTotal / peopleCount

return amountPerPerson
}

```


## Hiding the keyBoard 
