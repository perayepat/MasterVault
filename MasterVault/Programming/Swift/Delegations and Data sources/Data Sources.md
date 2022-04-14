# Overview 
Data sources source problems of inaccessible properties in classes , these are another use of delegations. 

Helps hold onto the data integrity 

Delegates only take values while data sources return values general rule that doesn't always work 

Generally used for UI and not necessarily  for objects 

**Definition**



A data source is a function that defines the data in a class 
returns the data you want to use 

![[Pasted image 20220328211653.png]]

**Note**
- *colorOfColor*
	 this allows the function to avoid having to deal with all the responsibility of making the array work right falls to the class adopting the protocol and that's why you're returning one value 




**Note**
Color no longer takes responsibility for setting the range of colors and that's passed to the user
![[Pasted image 20220328212709.png]]

how its implemented in the classes 
![[Pasted image 20220328213838.png]]

There's also no need to call colors from outside as you are doing that within the classes 
![[Pasted image 20220328213855.png]]


# Data sources and Delegates in Apps 
**Notes**

Pickers are one of the UI tools that use delegates and data sources 

![[Pasted image 20220328214521.png]]

**Note**
Each element on the picker is an individual component contained in an array, which show up on the picker wheel

![[Pasted image 20220328215012.png]]

![[Pasted image 20220328215803.png]]