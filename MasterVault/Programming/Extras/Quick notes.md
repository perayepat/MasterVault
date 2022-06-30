# Actors 
These help prevent data corruption when accessing one variable at a time by reading and writing to it.  Helps prevent data races too.  

*Example of memory corruption*
![[Pasted image 20220628132019.png]]

![[Pasted image 20220628132058.png]]

**Turning the counter into a actor**
solving the data problem where you are trying to access one variable to read and write to it 
![[Pasted image 20220628132142.png]]
