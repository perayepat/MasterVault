A property wrapper type that can read and write a value managed by SwiftUI. - > Taken from https://developer.apple.com/documentation/swiftui/state/ 

Overview Explanation: 
SwiftUI manages the storage of a property that you declare as state. When the value changes, SwiftUI updates the parts of the view hierarchy that depend on the value. Use state as the single source of truth for a given value stored in a view hierarchy.

A `State` instance isn’t the value itself; it’s a means of reading and writing the value. To access a state’s underlying value, refer to it by its property name, which returns the [`wrappedValue`](https://developer.apple.com/documentation/swiftui/state/wrappedvalue) property value. For example, you can read and update the `isPlaying` state property in a `PlayButton` view by referring to the property directly:

Basic Example of How states work: The example bellow shows how to change the text of the text object at runtime by linking it to a string variable which we edit. 

**struct** ContentView: View {

    @State **var** lblTimer: String = "Timer";

    **var** body: **some** View {

        VStack {

            Text(lblTimer)

                .padding().id("TimerLabel")

            HStack {

               Button("Start") {

                   StartTimer();

               }.background(Color.green).colorMultiply(Color.green).buttonBorderShape(ButtonBorderShape.roundedRectangle)

                Button("Stop") {

                    StopTimer();

                }.background(Color.red).colorMultiply(Color.red).buttonBorderShape(ButtonBorderShape.roundedRectangle)

            }.scaledToFill()

        }.scaleEffect(2.5)

    }

    **func** StartTimer() -> Void{

        lblTimer = "Start";

        }

  

    **func** StopTimer() -> Void {

        lblTimer = "Stop";                  

    }

}

  

**struct** ContentView_Previews: PreviewProvider {

    **static** **var** previews: **some** View {

        ContentView();

    }

}