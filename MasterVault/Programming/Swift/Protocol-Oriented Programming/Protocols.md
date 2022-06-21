# Overview 
They are kind of like certifications in a way.

when classes or structs adopt these protocols they can use these protocols and these certificates.


**Implantation**

protocols allow you to pass the capability to structs and classes that need them, they can also be used as data types in arguments and this allows them to be more useful

## Code 
``` Swift 
//this is the flying certificate that makes sure things that can fly can fly

//protocols aren't limited to classes or structs

**protocol** CanFly{

    //doesn't have an implementation

    **func** Fly()

}

  

**class** Bird {

    **var** isFemale = **true**

    **func** layEgg(){

      **if** isFemale{

            print("New bird spawned ")

        }

    }

}

  

  

**class** Eagle: Bird, CanFly{

    **func** Fly() {

        print("Eagles Flying")

    }

    **func** soar(){

        print("Fly using air currents")

    }

}

  

// penguin doesn't get the certification

**class** Penguin: Bird{

    **func** swim(){

        print("Swimming")

    }

}

  

**struct** FlyingMusem {

    //protocols can now use data types

    **func** flyingDemo(flyingObject: CanFly){

        flyingObject.Fly()

    }

}

  

//structs can't inherit protocols

//struct Airplane {

//

//}

  

**struct** Airplane : CanFly{

    **func** Fly() {

    print("Plane flys")

    }

}

  

**let** myEagle = Eagle()

**let** myPenguin = Penguin()

**let** museum = FlyingMusem()

**let** myPlane = Airplane()

  

myEagle.Fly()

myPlane.Fly()

museum.flyingDemo(flyingObject: myEagle)
```


# Highlighting the differences
![[Pasted image 20220621141436.png]]
