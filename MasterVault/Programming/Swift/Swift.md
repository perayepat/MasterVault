# Getting to know your data
## Variables and constants
![[Pasted image 20220307235853.png]]

Var - can be changed anytime 
let - constant which cannot be changed after  variable is assigned 

## Type safety and Inference
![[Pasted image 20220308000425.png]]

The swift language will guess the type of the variable but to lessen down on errors 

![[Pasted image 20220308000539.png]]
This tells the compiler that character name can only be a string to prevent miss matches 

![[Pasted image 20220308000717.png]]
noted as overkill 
![[Pasted image 20220308000741.png]]
declaring multiple variables is the same as C#

## Logging and Commenting 
![[Pasted image 20220308000856.png]]

Logging output to the print function is done through the *print* function

![[Pasted image 20220308000957.png]]

## Swift Operators 
![[Pasted image 20220308001639.png]]

## Understating String 
![[Pasted image 20220308003056.png]]

This is not limited to string just anything that can be turned into a string

## Working with strings
![[Pasted image 20220308003852.png]]

**Split**
this splits a string into an array where the string before and after are split into arrays
![[Pasted image 20220308004054.png]]

## Type Conversions 
cannot just convert double to int
int(double) 

loss of precision when a float looses its decimals 
String(double) - converts int to a string literal 

working with a double and a int one has to be made explicit to give the compiler enough information 
![[Pasted image 20220308004602.png]]

## Booleans and Logical Operators
![[Pasted image 20220308004915.png]]

## Introducing Optionals
optional tells the compiler that the variable is holding nothing 
- this can be used ass a place holder for future variables

Forced unwrapping is telling the compiler that it can unwarp the optional with no safety measures, don't form a habit of force unwrapping 

- They can be declared with any type 
![[Pasted image 20220308005340.png]]
## Challenge
![[Pasted image 20220308005557.png]]
![[Pasted image 20220308005603.png]]


# Working with Collections 
## Swift Arrays 
![[Pasted image 20220308172525.png]]

Arranging data in specific sequence 

The come with different styles
![[Pasted image 20220308172819.png]]

Accessing array values
![[Pasted image 20220308172917.png]]


## Core Array Methods
![[Pasted image 20220308173115.png]]
The arrays come with the standard methods that are in OOP 

Changing and adding items 
![[Pasted image 20220308173531.png]]

Inserting and removing Items 
![[Pasted image 20220308173602.png]]

Ordering and querying values
![[Pasted image 20220308173648.png]]

this returns a copy of the array
![[Pasted image 20220308173751.png]]

Contains 
![[Pasted image 20220308173810.png]]

**2d array and subscripts**
a simple 2d array 
![[Pasted image 20220308173934.png]]

jagged arrays don't need to be the same length 

****
## Dictionaries 
**Definition**
![[Pasted image 20220308174109.png]]

They are unordered 
Values are accessed by their associated keys 

**Creating a dictionary** 
empty dictionary 
![[Pasted image 20220308174314.png]]

![[Pasted image 20220308174439.png]]


They have the is empty and count variables

**Accessing and modifying values**

accessing a value 
![[Pasted image 20220308174548.png]]

When you update a non-existing item swift add it to your dictionary
![[Pasted image 20220308175851.png]]

**All keys and Values**
![[Pasted image 20220308175948.png]]

allKeys is going to be a dictionary, we can cast it to be an array of items 
Casting the dictionary output can be done 
![[Pasted image 20220308180141.png]]

When accessing a specific value in a dictionary :
![[Pasted image 20220308180400.png]]

## Core dictionary methods
**Definition**
![[Pasted image 20220308180504.png]]

**Caching and overwriting items**

Updating a dictionary 
![[Pasted image 20220308180741.png]]

This will override the items
![[Pasted image 20220308180848.png]]

**Caching and removing items**
Removing an item
![[Pasted image 20220308180921.png]]

**Nested dictionaries

The value for each key becomes a dictionary 
![[Pasted image 20220308181401.png]]
the ? after the fetch gemstones allows the compiler to return a nil if it doesn't find anything after searching for the item 

****
## Working with sets 
![[Pasted image 20220308181636.png]]

Similar to a Hashtable
![[Pasted image 20220308182146.png]]

**Creating sets**
Similar to a list when initialising 
![[Pasted image 20220308183656.png]]

type inference is different from other structures as you need to add the *set* so that it doesn't turn into an array 

**Inserting and removing elements**
you Done have to worry about indexes or key-value pairs 
the same goes for removing 
![[Pasted image 20220308183950.png]]

**More Common methods**
Checking for an item 
Sorting (this alphabetises a set, can also take predicates)
![[Pasted image 20220308184116.png]]

Sets can only store values that are hashable, all basic types are hashable 

## Core Set Methods
**Definition**
![[Pasted image 20220308184516.png]]

**Test variables**
these need a second set to work against
the second set doesn't need to be the same as the first 

**Set operations**
intersection - this finds the common value in both sets 
![[Pasted image 20220308184730.png]]

symmetric difference 
- this finds all the values that aren't similar in a set
![[Pasted image 20220308184826.png]]

Union operation
- combines the two sets 
![[Pasted image 20220308184959.png]]

Subtracting 
- Makes a new set minus the values from the second set 
![[Pasted image 20220308185127.png]]

Other methods are in the docs 

****
## Tuples
![[Pasted image 20220308185303.png]]

**Simple Tuple**
![[Pasted image 20220308185429.png]]
this contains indexes 

For when you don't know what a tuple is storing you can decompose it to make it more manageable

They need to be matched with the variable signature 
![[Pasted image 20220308185654.png]]

**Naming tuple variable**
individual names to the tuple variable or directly to the literal value 

type annotation approach
- this is where you add names 
- unlike the first where declared the variable types
![[Pasted image 20220308185904.png]]

Literal annotation approach
![[Pasted image 20220308190145.png]]

These approaches let you get the tuple by name, so you don't need to use the indexes or unpack them

**Naming values with type annotation**
![[Pasted image 20220308190306.png]]

**Uses**
- storing values returned from functions 
- Storing temporary variables
`its better to use classes and structs for larger projects`

## Challenge: Merchant Shop
![[Pasted image 20220308190621.png]]
![[Pasted image 20220308190710.png]]

**Solution**
![[Pasted image 20220308190946.png]]
![[Pasted image 20220308191147.png]]
![[Pasted image 20220308191226.png]]
![[Pasted image 20220308191331.png]]

# Control Flow
### NOTES
![[Pasted image 20220310000758.png]]

## The If statement 
**Definition**
![[Pasted image 20220309102741.png]]

ways to implement conditional code 
if the statement works exactly like python

**Test**
![[Pasted image 20220309105332.png]]

**or**
![[Pasted image 20220309105416.png]]

## Unwrapping optionals
**definition**
![[Pasted image 20220309105458.png]]

**Test**
![[Pasted image 20220309105517.png]]

**Optional Binding**
this is with a single string 
![[Pasted image 20220309105631.png]]

unwrapping multiple the catch is that they both have to be true in order to open them like && in C#
![[Pasted image 20220309105904.png]]

unwrapping our dictionary 
![[Pasted image 20220309110058.png]]

## For-in loops
**definition**
![[Pasted image 20220309110205.png]]
**Test**
![[Pasted image 20220309110407.png]]

string and arrays 
![[Pasted image 20220309110536.png]]

Dictionary and key pair values
![[Pasted image 20220309110711.png]]

using ranges
for every armour in armour, types go on until there's no more
![[Pasted image 20220309112113.png]]

## While loops
![[Pasted image 20220309112231.png]]

**test**
![[Pasted image 20220309112353.png]]

repeat while loops
repeats while the loop variable is valid 

![[Pasted image 20220309112435.png]]




## Switch statements 
![[Pasted image 20220309112618.png]]

**Test**
![[Pasted image 20220309112700.png]]
 simple switch case 
 ![[Pasted image 20220309113055.png]]
 they need to be exhaustive meaning they need to have the default statement 

Complex variations 
![[Pasted image 20220309113320.png]]

value binding is possible in swift and then need to be set up ![[Pasted image 20220309113832.png]]

## Guard statement 
![[Pasted image 20220309113915.png]]
**test**
![[Pasted image 20220309113928.png]]

Guard statement with a for-in loop
- the body has to have a return or have something in the body continue allows the loop to keep running 
- ![[Pasted image 20220309114138.png]]

## Game Logic 
**start**
![[Pasted image 20220309115830.png]]
![[Pasted image 20220309115848.png]]

the guard works like a shortened if 
for this guard, your players have to have more than one exp

# The wide world of functions
### Notes 
- go over closures , type aliasing  and function types 
## Basic Functions
![[Pasted image 20220309135037.png]]

**Basic Function**
- a basic function 
- adding a return type by adding a -> after the function call 
![[Pasted image 20220309135750.png]]

- adding function arguments to the function
![[Pasted image 20220309135850.png]]



## Overloading Functions 
![[Pasted image 20220309140002.png]]

**base function**
![[Pasted image 20220309140050.png]]

**Overloaded Function
![[Pasted image 20220309140214.png]]

## Complex functions 
![[Pasted image 20220309140324.png]]

**Optional return value**
![[Pasted image 20220309141255.png]]

**Multiple return values**
like returning a tuple 
![[Pasted image 20220309141504.png]]

**Default Values**
![[Pasted image 20220309141743.png]]

all these variations of functions can be combined 

## Function Types 
![[Pasted image 20220309141836.png]]

**function types** + **Using Functions as parameters**
![[Pasted image 20220309142217.png]]

Function types help separate code and keep it clean as possible 

## Understanding Closures 
![[Pasted image 20220309142352.png]]

**Defining Closures**
base closure 
![[Pasted image 20220309142842.png]]

defining a closure 
anything after the in is what's called from the closure 

**Initialising a closure**
![[Pasted image 20220309143227.png]]

compute bonus damage is referencing the compute bonus damage

shorthand 
![[Pasted image 20220309143343.png]]

## Using Closures 
![[Pasted image 20220309143424.png]]

**the sorted closure**
take the first and second and loops until the end, returning the ascending value 
Closures can be used to sort values in an array 
![[Pasted image 20220309143720.png]]


**Using closures with functions**
when a function takes in a closure, the parameters and statement body will be available when the function is called 

we need to call it in the body and add the string array 
![[Pasted image 20220309144213.png]]


this approach lets us edit data outside the declared scope,  we could declare the array and active members function and call active members in a different, were passing data from the active members to the closure we can access in any other class.

![[Pasted image 20220309144529.png]]

this is one way of passing data :

- the debug feature is stored in the completion enclosure and returned so we can capture it like any other type 

![[Pasted image 20220309144926.png]]
when capturing it we still need to call it like any other function that's the gotcha when it comes to capturing them 

Returning a closure this was is more niche as they are used for input variables commonly

**Version 2**
- it's similar to a lambda 
- a closure is a function that can be passed around
![[Pasted image 20220309162102.png]]

- helps simplify a function 
![[Pasted image 20220309162356.png]]

myFunction takes in an int parameter and returns a bool, turning a function into a variable 
- number in the closure becomes a parameter that could be named anything 
- myFunction results in a bool

it could also return a void where it does something in the background and is decoupled 
![[Pasted image 20220309162823.png]]

- even though its a function it's treated as a variable
![[Pasted image 20220309162946.png]]

![[Pasted image 20220309163250.png]]

it can be re-assigned 

**function vs closure**
you don't need to add the number: 4
and makes it more flexible 



## Type aliasing 
![[Pasted image 20220309145211.png]]

**type aliasing as a return value**
can also be used as an input parameter type and a return type 
![[Pasted image 20220309151313.png]]

**Type alias as a function parameter**
![[Pasted image 20220309151413.png]]

![[Pasted image 20220309160931.png]]

![[Pasted image 20220309160953.png]]

No with this we've created our own type that's a string
![[Pasted image 20220309161217.png]]
![[Pasted image 20220309161249.png]]
![[Pasted image 20220309161437.png]]
this is the simplification of the underlying type, the underlying type is a dictionary 

![[Pasted image 20220309161541.png]]
- simplifying this 
- Using a type alias
![[Pasted image 20220309161649.png]]

it becomes easier to use the closure to verify the promotion code 
![[Pasted image 20220309161810.png]]

can be used across different files

****
## Challenge: battlegrounds 
![[Pasted image 20220309155553.png]]

# Classes, Structs and Beyond 
![[Pasted image 20220310121905.png]]


![[Pasted image 20220310121934.png]]

**Passing Value types**
![[Pasted image 20220310122026.png]]

passing value types it passing an exact copy of that object 

**Reference type**
![[Pasted image 20220310122117.png]]

Whatever happens to your avatar is what will happen to you

![[Pasted image 20220310122543.png]]

## Access modifiers and properties 
![[Pasted image 20220310125641.png]]

## subclassing 
![[Pasted image 20220310131202.png]]
## Structs 
![[Pasted image 20220310131844.png]]

structs are value types and classes are reference types 

## Optional Chaining 
![[Pasted image 20220310133545.png]]
# Enums , Protocols and Errors
## Swift enumerations
![[Pasted image 20220310200830.png]]

## Raw and associated values 
![[Pasted image 20220310201819.png]]

## Introducing Protocols
![[Pasted image 20220310204726.png]]

## Throwing Errors
![[Pasted image 20220310212404.png]]

## Handling Errors
![[Pasted image 20220310212903.png]]

# Delegations and data sources 
[[Programming/Swift/Delegations and Data sources/Basics]]

# Delegations 
[[Delagations]]

# Data Sources
[[Data Sources]]

