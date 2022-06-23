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