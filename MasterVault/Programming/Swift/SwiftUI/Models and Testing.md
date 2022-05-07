# State Variables and buttons 
**Links :**
[`Understanding State`](https://martinlasek.medium.com/swiftui-understanding-state-8afa23fd9f1f)
[[@States]]

**State Variables**
 - Instead of an event causing an action, a state variable triggers the view to change to redraw with the new values. 
- Mainly used with buttons 



# Dynamic collections 
**LInks:**
[`Documentation`](https://docs.swift.org/swift-book/LanguageGuide/CollectionTypes.html)


This is one way of creating an array of SF Symbols that create an array while also creating a variable, This method can also be used for ordered images and ordered content.

``` Swift 
var rating:[String]{
	let symbolName = "\(count).cirlce"
	return Array(repeating:symbolName, count:count)
	}
```

Notes: 
- the *id.|self* solves the identifiable issue which shows up in *foreach* and *lists*
![[Pasted image 20220507171404.png]]

# Identifiable Protocol 
[`Video Explanation`](https://youtu.be/zrJG7EyMPLI)

**The problem is solves** 
This swift protocol deals with the problem of having an array that may contain variables with the same name, This is a problem because you can have to overwrite issues and the swift might not know which value to change and changes all of them because it treats the name as an identifiable variable. 

![[Pasted image 20220507172730.png]]
*Fig 1, Example problem*

Notes : 
- The list view knows which item you're swiping on, so ids aren't necessary. 

**Solution**
Adding a unique id number to the struct and the *Identifiable Protocol* solves the problem above where the name is being used as the identifier. 

When conforming to identifiable the one requirement is having an id property.
```swift
struct ExpenseItem: Identifiable {
    let id = UUID()
    let name: String
    let type: String
    let amount: Int
}
```

Notes: 
 - it also means you don't have to have the id in the foreach since each expense item is now unique and conforms to *identifiable*. 

![[Pasted image 20220507173806.png]]
*Fig 2,  Example Solution*

# Navigation
**Links:**
<iframe width="560" height="315" src="https://www.youtube.com/embed/nA6Jo6YnL9g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Concise and clear explanation. 

# Binding Variables
**Links:**
[`What is the @Binding`](https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-binding-property-wrapper)
[`Understanding Binding`](https://martinlasek.medium.com/swiftui-understanding-binding-8e20269a76bc)
[`Video Example`](https://www.youtube.com/watch?v=lgtB3WLEOYg)

``` Swift
@Binding 

// This wrapper allows you to pass a value from one view to another 
```

**Problem**
The problem it solves is changing a value you have in another swift class and wanting to change it in another swift Class which will then cause an action to occur in this class. 

Example: 

You want the add user view to dismiss itself when it needs to. 
When the `showingAddUser` is set back to false it will make the content view hide it.
```swift
struct ContentView: View {
    @State private var showingAddUser = false

    var body: some View {
        VStack {
            // your code here
        }
        .sheet(isPresented: $showingAddUser) {
            // show the add user view
        }
    }
}
```
*Fig 1, Example problem*

**Solution**

Notes:  

- This allows both `ContentView` and `AddView` to share the same Boolean value – when it changes in one place it also changes in the other.

- now you have a view that dismisses itself when the user presses the done button.

```swift
struct AddView: View {
    @Binding var isPresented: Bool

    var body: some View {
        Button("Dismiss") {
            isPresented = false
        }
    }
}
```


This replaces the `sheet` in the example problem 
```swift
.sheet(isPresented: $showingAddUser) {
    AddView(isPresented: $showingAddUser)
}
```

# ObservedObject
**Links:**
[`Video Explanation`](https://youtu.be/OvLxxV7X1Is)
[`Documentation Explination`](https://www.hackingwithswift.com/quick-start/swiftui/what-is-the-observedobject-property-wrapper)

`@ObservedObject` allows swift to view the state of an external object and be notified of the change.

Similar to `@State` but it's not used to create objects. `@ObservedObject` is only to be used with an object created elsewhere. 

Example : 

Notes: 
 - That `Order` class uses `@Published` so it will automatically send change announcements when `items` change and `ContentView` uses `@ObservedObject` to watch for those announcements. Without `@ObservedObject` the change announcements would be sent but ignored.
 
 - Designed so that data can be shared across more than one view.
 - `@Pusblised` will insure that the observed object is watched in a class with the  `@ObservableObject`.  
```swift
class Order: ObservableObject {
    @Published var items = [String]()
}

struct ContentView: View {
    @ObservedObject var order: Order

    var body: some View {
        // your code here
    }
}
```

# EnvironmentObject 

**Links:**
[`How to use @EnvironmentObject to share data between view`](https://www.hackingwithswift.com/quick-start/swiftui/how-to-use-environmentobject-to-share-data-between-views)
[`Video Explanation`](https://www.youtube.com/watch?v=e2lQtUdK1uI)

For data that should be shared with many views in your app, SwiftUI gives us the `@EnvironmentObject` property wrapper. This lets us share model data anywhere it’s needed, while also ensuring that our views automatically stay updated when that data changes.

a simpler way of using `@ObservedObject` on lots of views.

Example :
```swift
// Our observable object class
class GameSettings: ObservableObject {
    @Published var score = 0
}

// A view that expects to find a GameSettings object
// in the environment, and shows its score.
struct ScoreView: View {
    @EnvironmentObject var settings: GameSettings

    var body: some View {
        Text("Score: \(settings.score)")
    }
}

// A view that creates the GameSettings object,
// and places it into the environment for the
// navigation view.
struct ContentView: View {
    @StateObject var settings = GameSettings()

    var body: some View {
        NavigationView {
            VStack {
                // A button that writes to the environment settings
                Button("Increase Score") {
                    settings.score += 1
                }

                NavigationLink(destination: ScoreView()) {
                    Text("Show Detail View")
                }
            }
            .frame(height: 200)
        }
        .environmentObject(settings)
    }
}
```