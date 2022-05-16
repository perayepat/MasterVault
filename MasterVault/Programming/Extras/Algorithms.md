
# Notes
- Knowing more about your data allows you to make educated assumptions that will lead to a more optimal path
# Introduction
![[Pasted image 20220208135144.png]]
big O is used to describe space complexity aswell.

# String Algorithms 
## Validation Algorithm
![[Pasted image 20220208140848.png]]
## Normalize strings
![[Pasted image 20220208140946.png]]
- Limit input to a certain type and then use a validation to only accept one use 
- Algorithms should be flexible 
- Makes it more flexible and the data easier to use 


## Parse and Search string 
![[Pasted image 20220208141739.png]]
![[Pasted image 20220208143032.png]]

## Create algorithm-driven string 
![[Pasted image 20220208144605.png]]
![[Pasted image 20220208144746.png]]


# Array Algorithms 
## Liner Search 
- Also known as sequential search one after another
## Binary Search 
![[Pasted image 20220208151653.png]]
	- Looking for the number 45 it would start at the middle index and determine whether the middle index is greater than or lesser than the number being searched for then it would go to the right since the numbers are sorted in ascending order.
![[Pasted image 20220208152005.png]]
![[Pasted image 20220208153401.png]]
- we're assuming it's sorted in ascending order 
- How long would the sorting take compare to a normal search? 
- Are you doing multiple searches if not a linear search would be optimal?

## Aggregate and filter arrays 
![[Pasted image 20220208153700.png]]
- combining multiple data sets to one data set 
![[Pasted image 20220208153819.png]]
![[Pasted image 20220208153853.png]]

## Reverse an Array 
![[Pasted image 20220208155431.png]]
- moving data from in place is essential for efficient
- 
- 
-  algorithms 


# Que and Stack 
- Good for processing data from the way it was received 
- Reduce complexity by using First In First Out Method
![[Pasted image 20220211110836.png]]
![[Pasted image 20220211110935.png]]
![[Pasted image 20220211110943.png]]
![[Pasted image 20220211111041.png]]


**Stack**
- Useful when you need to keep track of state, as a list 
- The state can be a condition, E.g. if numbers are greater than the next or lesser
- Has matching parentheses 
![[Pasted image 20220213190120.png]]

![[Pasted image 20220213190141.png]]
![[Pasted image 20220213190204.png]]
![[Pasted image 20220213190318.png]]
# Hash-Based Structures
![[Pasted image 20220213195332.png]]
****
**HashSet**![[Pasted image 20220213195504.png]]Collection of unique items 
Cannot contain duplicates 
and order doesn't matter 
unique Id and order doesn't matter 
![[Pasted image 20220213195643.png]]
**Dictionary**
![[Pasted image 20220213195744.png]]
Store each employee value with an ID and search for them in constant time by using key value's
****
**Hashtable vs Dictionary**
![[Pasted image 20220213200030.png]]
- They both store key-value pairs 

****
![[Pasted image 20220213200138.png]]


****
HashSet
- Working with questions of membership a HashSet 
- ![[Pasted image 20220214120714.png]]
****
**Dictionary**
![[Pasted image 20220214122320.png]]
![[Pasted image 20220214130921.png]]
# Tree
- **Binary Tree**
 ![[Pasted image 20220216150104.png]]
- **Binary Search Tree**
![[Pasted image 20220216150135.png]]
![[Pasted image 20220216150143.png]]
![[Pasted image 20220216150230.png]]
![[Pasted image 20220216150254.png]]
![[Pasted image 20220216151737.png]]
![[Pasted image 20220216151746.png]]
**Traversing a Tree**

![[Pasted image 20220216151907.png]]
![[Pasted image 20220216151923.png]]
![[Pasted image 20220216152035.png]]
![[Pasted image 20220216152115.png]]
![[Pasted image 20220216152143.png]]
![[Pasted image 20220216152557.png]]
- **Maximum Depth Search**
	![[Pasted image 20220217181157.png]]
	![[Pasted image 20220217181219.png]]
	![[Pasted image 20220217181331.png]]
# Challenges 
![[Pasted image 20220208155750.png]]
![[Pasted image 20220208162917.png]]- Save the first item in the array as a temp variable 
- Move the items after the temp to where the time used to be 
- once you reach the end add the temp to the end 

![[Pasted image 20220213191108.png]]
![[Pasted image 20220213191206.png]]
![[Pasted image 20220213191521.png]]
- This gives us a linear time complexity
- ![[Pasted image 20220213193354.png]]

[[Linked List Algorithms]]