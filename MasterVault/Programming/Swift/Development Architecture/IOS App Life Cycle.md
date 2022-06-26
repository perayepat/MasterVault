# Overview 
![[Pasted image 20220622073832.png]]

first steps of the startup sequence
![[Pasted image 20220622074627.png]]

# Main Run Loop
This is created by the UI application object in the app initialization 
![[Pasted image 20220622081023.png]]
![[Pasted image 20220622081044.png]]

# Architectural Design Patterns
## Overview 
![[Pasted image 20220622082156.png]]

**Commonly used design patterns**
They all have one thing in common which is separating the concerns within our app.
![[Pasted image 20220622082325.png]]

## Model View Controller 
**sources**
	<iframe width="560" height="315" src="https://www.youtube.com/embed/azFmaTZUy7k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
**The View**
Any UI view or UI view subclass can be considered a view 

![[Pasted image 20220622082505.png]]


**The Model**
this contains the data we might be getting from an api or any other source of data 
![[Pasted image 20220622082645.png]]

**The Controller**
this chooses how the data in the model should be displayed. The model is unaware how the data should be viewed, Converting user input to interact with the model and return data 
![[Pasted image 20220622083040.png]]


**Graphical Representation**
![[Pasted image 20220622083051.png]]
![[Pasted image 20220622083059.png]]
![[Pasted image 20220622083107.png]]

**Pitfalls**
When too many components or tasks are used in the the controller , this design pattern begins to get bloated and that when alternatives to this pattern become more useul.
![[Pasted image 20220622083259.png]]
## The Model View Presenter
 Sources
	<iframe width="560" height="315" src="https://www.youtube.com/embed/SFqIP5jYn_4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


**Overview**
![[Pasted image 20220622083501.png]]

**The View in MVP**
![[Pasted image 20220622083620.png]]

**The Presenter**
![[Pasted image 20220622083644.png]]


## The Model View ViewModel
![[Pasted image 20220623144226.png]]
![[Pasted image 20220623144559.png]]
**Key Differences**

MVVM Provides two way data binding.

*Ways to implement data bindings in iOS :*
 - key value observing 
 - notifications 
 - Delegation

These binding s help update the views automatically after a set amount of seconds in Story Boards 

# App Delegate
## Overview

This is a singleton object that's created whenever we create an app. 

**Uses**

Helps us react to different state changes such as the app being closed, the app being in the background and or the app restarting. 

These calls can all be deleted and except for : `didFinishLaunchWithOptions`

State preservation and restoration can all be done in the app delegate.  

## State changes

**Possible states of an IOS app**

- Starts into not `running` into `Inactive`

- Once the start up logic and the state restoration finish the app then goes into the `active` state.

- The app switches to the `background` for various reasons , the app is not terminated but can still execute shore tasks.

-  Form `not running` and `Background` to reach the active state `inactive` is  needed to complete state restoration and logic to reach active. 

- Force quit takes the app to `suspended` then terminates the app without any notification 

![[Pasted image 20220623152003.png]]

**IOS app State machine**
this shows all the possible state and what triggers those transitions.

![[Pasted image 20220623152657.png]]
# Building Responsive Apps
## The main UI thread
**Main thread Overview**
 - The main thread is reserved for UI related tasks ,
 -  task like file IO and asynchronous tasks shouldn't run on the main task because they make animations and other tasks slow 
 ![[Pasted image 20220623155047.png]]

**Best Practices**
![[Pasted image 20220623162627.png]]

**GCD**

this allows tasks to be submitted to a queue which are then executed in a FIFO order 

![[Pasted image 20220623162650.png]]

**Dispatch Queue**

*How it works :*

Concurrent queue 
	- the user tasks are executed asynchronously.  
	- the control  returns to the caller.
	- the concurrent queue can execute other tasks in parallel  with the currently submitted one.

Serial queue 
	- the concurrent queue and the task execute synchronously and one task is done at a time until the main one is completed. 
	- the concurrent queue can execute other tasks too. 

![[Pasted image 20220623162800.png]]


**Serial Queue**
![[Pasted image 20220623163335.png]]

## Deadlocks
Submitting a task synchronously causes tasks to become dead locked and this freezes the app.

A task implementing on the same queue causes a dead lock

**Cause and use cases**
To prevent deadlock don't call a synchronous queue on the same
queue `viewDidLoad`  
![[Pasted image 20220623165442.png]]

# The SOLID Principles
## Overview
![[Pasted image 20220623165925.png]]

**SOLID**
theses are 5 fundamental object orientated programming principles that help solve bad design problems. 

Pillars of well written object oriented code 

![[Pasted image 20220623170104.png]]

## Single Responsibility Principle 
![[Pasted image 20220623170209.png]]

implementation 
Separating functionality of a class makes it easier to understand and refactor code if need be. 

Changes are isolated to smaller units. 

![[Pasted image 20220623170302.png]]

## Open/Close Principle
**Overview**

This means new features are added by adding new code and not by modifying the existing code.
![[Pasted image 20220623170557.png]]

Swift extensions are a great way of adding new features 

![[Pasted image 20220623170643.png]]

we can enhance types we don't own 
![[Pasted image 20220623170701.png]]

## Liskov Substitution Principle
**Overview**
![[Pasted image 20220623170754.png]]

**implementation**
![[Pasted image 20220623170823.png]]

the different types of shapes derive from shape
because all these shapes derive from shape they are able to be used in a array that uses their base class and then use that array to calculate their total area 
![[Pasted image 20220623171022.png]]

## Interface Segregation Principle 
**Overview**

This deals with an interface that exposes to many properties, this can effect our type and protocols.
![[Pasted image 20220623171337.png]]

**Implantation**

using the image Protocol what if we don't need the base64 encoded 

or 
Retrieving the Jpg image data 

![[Pasted image 20220623171449.png]]

the solution is to expose the narrowest interface
![[Pasted image 20220623171535.png]]

we can split the protocol into separate protocols  
![[Pasted image 20220623171633.png]]

clients can choose which protocols they want to adopt : 

*The Encodable Image* and the *Base64EncodeablePersistableImage*

these use composition to call the protocols they need instead of calling the bulky first protocol.
![[Pasted image 20220623171835.png]]
- default behavior can be executed using extensions. 

## Dependency Inversion Principle
**Overview**
![[Pasted image 20220623172024.png]]

**Implementation**

![[Pasted image 20220623172039.png]]
- The persistence class can save objects of data to specific destination using a string
- The persistence class uses the logger class to print out log messages 
- Persistence is High level and logger is Low level 

The goal becomes to decouple the Logger class and the Persistence class

**solution to tight coupling**
Introducing a swift protocol that uses holds the logging functionality.
![[Pasted image 20220623172447.png]]

`Persistance` now refers to a protocol instead of a concrete type

we pass the logging object through the `init`
this allows us to use persistence in any class ad use persistence with any other type of `Loggger`

*Useful for testing*

# Communication between Apps
## Overview

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZZNSakE329w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


![[Pasted image 20220623174626.png]]

These sharing schemes won't work because of iOS security 
![[Pasted image 20220623174706.png]]

## Calling an app from another app
using the the url scheme you are about to open your app from another app 

![[Pasted image 20220623175444.png]]
Linking this to a button will open your app from another app 

**Pitfalls**

you should always query if the app is installed or available before trying to open it using the URL. 

![[Pasted image 20220623175712.png]]

## URL Scheme whitelist 
If we want to look up a specific URL scheme we need to add it to the white list.

The white list can only contain certain number of URLs. 

using the PList

## Passing parameters between the apps

while this works this is limited to the parameters passed in the query string. 
**Sources**
	<iframe width="560" height="315" src="https://www.youtube.com/embed/UVIQ7fkw_N8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
	
we can pass parameters between apps using a query strings
  <iframe width="560" height="315" src="https://www.youtube.com/embed/Kr3G9C22_-Q" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
## Airdrop 

  <iframe width="560" height="315" src="https://www.youtube.com/embed/wpfsN5najB4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Efficiency and Performance
When memory warning happens the best thing to do is to clear all caches 

**Profiles**
can be used to see how to optimize your app 