# Forms 
Scrolling lists of static views such as images and text fields but they can also have more dynamic things like toggle views and switches.

``` Swift
// Forms can only take 10 items 
Form{
	Text("Hello World")
}
```
![[Pasted image 20220516094649.png]]


To split the items in a form you can use `Groups` or `Sections`, these allow you to have more than  10 items in a form. These are work around the 10 Items restriction


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
Groups look the same as a normal form and items arent split up 


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
Sections however will split the view up like the setting view in your Iphone 


# Navigation View
Used to nvaigate between views 

``` Swift
NavigationView{
	Form{
		Text("Hello World")
	}
	.navigationTitle("Title")
	//The navigation title goes inside the nav view not outside 

}
```

# Modifying program state
The active collection of changes and setting in programing is the state.
These describe how the ui look at the current state

*E.g.  They can't do A until they complete B*
