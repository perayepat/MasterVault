# Common Algorithms 
![[Pasted image 20220220153815.png]]
![[Pasted image 20220220153831.png]]

**Euclid's Algorithm**
![[Pasted image 20220220153950.png]]
![[Pasted image 20220220154012.png]]

****
**Understanding Algorithms Performance**
![[Pasted image 20220220155234.png]]
![[Pasted image 20220220155259.png]]

**Big O notation terms**
![[Pasted image 20220220155323.png]]


# Common Data Structures 
## Overview 
![[Pasted image 20220220160040.png]]


## Arrays 
![[Pasted image 20220220160442.png]]

**2 Dimensional Array**
![[Pasted image 20220220160508.png]]

**Array Operations**
![[Pasted image 20220220160556.png]]

## Linked List 
![[Pasted image 20220220160623.png]]
**Doubly linked list**
![[Pasted image 20220220160724.png]]

**Overview**
![[Pasted image 20220220160808.png]]

**Removing and adding a node to the start**
![[Pasted image 20220220160902.png]]

## Stacks and Queues 
**Stack**
![[Pasted image 20220225112349.png]]
**Queue**
![[Pasted image 20220225112423.png]]

**Practical Applications**
**stack**
- The browser adds links to a stack to be able to go back or see a breadcrumb trail 
**Queue**
- Sending Messages in a particular order 

![[Pasted image 20220225112619.png]]

## Hash Tables 
![[Pasted image 20220225113809.png]]
**Explanation**
- each key is mapped to an individual spot but sometimes collisions happen and this is when the same key is mapped to the same value 

**Definition**
Faster than any other look up table for large amounts of data for smaller data an array would be best 

They can be used progressively to grow and shrink to fit in the data they need 
![[Pasted image 20220225114121.png]]


# Recursion
## Intro
![[Pasted image 20220225115718.png]]

**Examples Finding a folder in a directory**
![[Pasted image 20220225115814.png]]

- You don't have to keep track of all the files visited 

![[Pasted image 20220225115913.png]]

**Example 2**
Count Down 
![[Pasted image 20220225120019.png]]

## Simple Example
![[Pasted image 20220225120950.png]]
Countdown Timer

## Power and Factorial 

![[Pasted image 20220225121803.png]]

# Sorting Data
## Intro 
- Sorted data allows data to be retrieved efficiently 
![[Pasted image 20220225121943.png]]

Unlikely you'll have to build your own sorting algorithm
![[Pasted image 20220225122022.png]]
More algorithms out there 
## Bubble Sort
![[Pasted image 20220225122120.png]]
The values bubble their way to the top 
**characteristics**
- Bad performance in O(n2)
- ![[Pasted image 20220225122224.png]]

## Merge Sort 
![[Pasted image 20220225122934.png]]

**example**
Merging two arrays together 
![[Pasted image 20220225123507.png]]

![[Pasted image 20220225123530.png]]

## The Quicksort
![[Pasted image 20220225125728.png]]

**Characteristics**
It picks a pivot position 
Where the indexes cross is the pivot point 
![[Pasted image 20220225130112.png]]

# Searching Data
## searching a sorted list 
**Binary Search**
this is more efficient for searching a ordered list 
![[Pasted image 20220301161831.png]]
![[Pasted image 20220301161843.png]]
**order of operations**
find the midpoint 
if the midpoint is found return the index if not 
find the next midpoint 
![[Pasted image 20220301162533.png]]
log of N 
very efficient 

## Identifying a sorted list 
![[Pasted image 20220301164151.png]]

# Other Algorithms 
## Unique filtering with hash tables 
![[Pasted image 20220302214904.png]]
big 0 of N
## Value counting with hash-tables
![[Pasted image 20220302215154.png]]
add up the value for every time

we encounter a value   

## Find max recursively
![[Pasted image 20220302215846.png]]

