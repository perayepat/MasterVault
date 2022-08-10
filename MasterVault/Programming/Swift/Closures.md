# Closures
## Overview

**Closure Syntax**

```ad-tip Swift
	{(parameter) -> return type in 
		statement 
	}
```


Closures allow you to pass other functions as arguments in one method an example of this would be : 

``` Swift 
func calculator(n1: Int, n2: Int, operation: (Int,Int) -> Int) -> Int {
 return operation(n1,n2)
}

func add(no1: Int, no2: Int) -> Int {
 return no1 + no2
}

func multiply (no1: Int, no2: Int) -> Int {
return no1 * no2
}

calculator(n1: 2,n2: 3, operation: add)
```

When we want to simplify it and make it easier to read we can  : 

``` Swift 
func calculator(n1: Int, n2: Int, operation: (Int,Int) -> Int) -> Int {
 return operation(n1,n2)
}



calculator(n1: 2,n2: 3, operation: { (no1: Int, no2: Int) -> Int in
 return no1 + no2
})
```

Allowing swift to use type inference we can shorten our code to an even shorter state

```ad-tip  Swift 
//USing type inference

calculator(n1: 2, n2: 3, operation: { (no1, no2)  in

  no1 + no2

})
```

``` ad-tip  Swift 
//Even more cut down using type inference 

let result = calculator(n1: 2, n2: 3, operation: { $0 * $1 })


print(result)
```

```ad-tip Swift
	let result2 = calculator(n1: 2, n2: 3) { $0 * $1 }
```

**MAP**
This function transforms every single item in an array 


Heres is an example of using the Map function in conjunction with closure to make code quicker to write:

```  Swift
	//MARK: Using MAP**

  

	let array = [6,2,3,9,4,1]

  

	func addOne (n1: Int) -> Int {

	return n1 + 1

	}

  

	array.map(addOne)

  

// Using closures

	array.map { num **in** num + 1}

// short form array.map { $0 + 1}

//MARK: Converting the Int's into Strings**
	let newArray  =  array.map {"\($0)"}
```


