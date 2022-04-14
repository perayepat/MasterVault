How does swift handle a cluster of controllers?

# Delegations view controller in code
This code lets us access the other view controller which is n charge of creating another view where we can select our colors 
This allows you to move from one class to another using the modal presentation 
![[Pasted image 20220327170604.png]] 

moving the safe gaurd to the return 
![[Pasted image 20220327171121.png]]


This is the second view controller 
![[Pasted image 20220327171153.png]]

# Destination view controllers in storyboards
# Delegation in theory 
Delegates help  move data from the destination to the source, a function called in one class that runs in another  allows sharing of data 

**Protocols**
a skeleton of a class but never implements them 

Any class can make a protocol a part of themselves
in the destination view controller make an instance of the protocol as a property of the destination class 
With the property used in the destination 


Then we adopt the protocol in the source controller then make the skeleton for the protocol class.


![[Pasted image 20220327174331.png]]
# Delegation in Code
 Exercise files 02_05
 moving data from one controller to another
**Look more into delegates as they are very important**


