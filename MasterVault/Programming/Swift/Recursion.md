
# Fibonacci recursive function
**Used to illustrate the concept of recursion**
## Sources
<iframe width="560" height="315" src="https://www.youtube.com/embed/Qk0zUZW-U_M" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
https://www.weheartswift.com/recursion/

## Overview 
if you put a pair of rabbits in a vast field covered in the grass they will reproduce like mad and the number will grow in a Fibonacci sequence.

`Function construction`
![[Pasted image 20220620101451.png]]

Eg1
![[Pasted image 20220620102841.png]]

The next term is the sum of the two previous terms which goes on forever. 

![[Pasted image 20220620102953.png]]
The goal is to make it fast and clearly written. 

this function becomes exponentially slow the higher the number becomes.
![[Pasted image 20220620103308.png]]
![[Pasted image 20220620103411.png]]

- the reason it's slow is that it repeats itself needlessly

**Solution**

Memoisation 
- store the values from recent function calls so future function calls have less work to do. 

*The example used is in python*

![[Pasted image 20220620103738.png]]
- the case stores recent function calls 



 


# Factorial 
