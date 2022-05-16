# State variables and buttons
Link : [`State Explained`](https://martinlasek.medium.com/swiftui-understanding-state-8afa23fd9f1f)
LinkedIN Learning :   SwiftUI Essential Training 

in this example the @State variable is being used change the name from one name to another. 

 Notes : 
  - all state variables must have a value to start they cannot be left blank
  - The button will be used to control the state 

``` Swift
struct ContentView : View {  
  @State var pokemonName = "Charmander" 
   
  var body: some View {  
    VStack {  
      Text(pokemonName)  
        .frame(  
          width: UIScreen.main.bounds.width,  
          height: 50  
        )  
        .background(Color.blue)  
        .foregroundColor(Color.white)  
        .padding(10)      
         Button(  
        action: { self.switchPokemon() },  
        label: { Text("Switch") }  
      )  
    }  
  }  func switchPokemon() {  
    **let list = ["Squirtle", "Bulbasaur", "Charmander", "Pikachu"]  
    pokemonName = list.randomElement() ?? ""**  
	  }  
	}
}
```

![[Pasted image 20220502165058.png]]
*Fig 1 Changed*
![[Pasted image 20220502165822.png]]
*Fig 2 Unchanged*


**Example 2**
@State is being used to collapse and expand  a view using the *Layoutpriority*

Notes : 
-  Toggle is used to switch between true and false 
- Whenever there is a change in state the menuListView and the order list view will  redraw based on the value of is isMenuDisplayed 

- The values are switched in the layoutPriority between MenuListView and OrderListView to make sure one of them is showing at a time. 
``` Swift
@State var isMenuDisplayed:Bool = true

var body : some View {
		Vstack{
		ContentHeaderView()
			.layoutPriority(2)
			
		Button(action:{self.isMenuDisplayed.toggle()})
		{
		PageTitleView(title: "Order Pizza")
		}
		
		MenuListView()
			.layoutPriority(isMenuDisplayed ? 1.0 : 0.5)
		OrderListView()
			.layoutPriority(isMenuDisplayed ? 0.5 : 1.0)
		
	}
}
```

![[Pasted image 20220502170304.png]]
*Fig 1 No change*
![[Pasted image 20220502170332.png]]
*Fig 2 Change*

**Example 3**

This is using a local variable instead of a state variable to change the icon using a bool

This is the PageTitleView Class and from here this bool to change the icon will be used in the contentView to change the icon 

![[Pasted image 20220502171650.png]]
*Fig 1 Page Title View*

![[Pasted image 20220502171906.png]]
*Fig 2 Content View*





