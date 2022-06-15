
# Overview
Used to reduce memory use and when a common pool of objects share the same data but are going to vary once the app or game has started. 

Minimizes memory usage by sharing common immutable data among multiple objects 
![[Pasted image 20220615061115.png]]

To make it work you need to separate the unchanging parts from the data
![[Pasted image 20220615061356.png]]
![[Pasted image 20220615061408.png]]

**Example**
we can have a fleet of ships that share the same mesh and texture but the positions are different and may also change.
![[Pasted image 20220615061548.png]]
the ships the mesh and texture are intrinsic but the position and speed are extrinsic.

![[Pasted image 20220615061728.png]]