A timer that fires after a certain time interval has elapsed, sending a specified message to a target object. Get more information on timers here -> https://developer.apple.com/documentation/foundation/timer/

Timer in use example:

**struct** ContentView: View {

    @State **var** hours: Int = 0

    @State **var** minutes: Int = 0

    @State **var** seconds: Int = 0

    @State **var** timerIsPaused: Bool = **true**

    @State **var** timer: Timer? = **nil**

    **var** body: **some** View {

        VStack {

            Text("\(hours):\(minutes):\(seconds)")

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

        timerIsPaused = **false**

            timer = Timer.scheduledTimer(withTimeInterval: 1, repeats: **true**){ tempTimer **in**

              **if** **self**.seconds == 59 {

                **self**.seconds = 0

                **if** **self**.minutes == 59 {

                  **self**.minutes = 0

                  **self**.hours = **self**.hours + 1

                } **else** {

                  **self**.minutes = **self**.minutes + 1

                }

              } **else** {

                **self**.seconds = **self**.seconds + 1

              }

            }

        }

  

    **func** StopTimer() -> Void {

            timerIsPaused = **true**

            timer?.invalidate()

            timer = **nil**

    }

}

  

**struct** ContentView_Previews: PreviewProvider {

    **static** **var** previews: **some** View {

        ContentView();

    }

}