# What is grand central dispatch
![[Pasted image 20220629121741.png]]

## Adding multithreading 
![[Pasted image 20220629121816.png]]
![[Pasted image 20220629121828.png]]
![[Pasted image 20220629121844.png]]
## What are queues 
![[Pasted image 20220629123234.png]]
![[Pasted image 20220629123247.png]]
Queues are worked on in the same order they were put in, 


Serial and Concurrent queues 
**Serial queues**
finish tasks in the order they were inputted 

**Concurrent queues**
These don't finish tasks in the way they were started 

![[Pasted image 20220629123859.png]]
![[Pasted image 20220629123914.png]]
 ![[Pasted image 20220629124215.png]]

## The main queue
The main thread is created when the app is created and the main thread is given the highest priority in terms of quality of service and what goes on the main thread.  

![[Pasted image 20220629124323.png]]

Found in the app delegate 
![[Pasted image 20220629124548.png]]


**Best practices**
![[Pasted image 20220629124619.png]]

Example 
![[Pasted image 20220629124715.png]]
logging in a user from a network call and logging them in from one screen to another, 
The network call is done on a background thread and then pushes to the main thread when the call is received.


**Main thread checker**
this is a swift tool to check weather we are using the main thread or not 
![[Pasted image 20220629124953.png]]

![[Pasted image 20220629125008.png]]
**Async**
Calls on background thread for completion and ensures the main thread is never blocked. 

**Sync**
Completes tasks in order and waits for one task to be completed before completing the other. This will block the main thread and cause UI to be slow and lagy. 
## The global Queue 
Grand Central Dispatch provides us the global queue to work with. 

the global queue is a concurrent queue that completes queues depending on the priority of the task. 

We determine the task priority by using  `qos` 
![[Pasted image 20220629125446.png]]
![[Pasted image 20220629125453.png]]


There are four main types of quality of service and one default 
![[Pasted image 20220629125545.png]]

**.1**`.userInteractive`
The fastest one is `.userInteractive` tasks that have this priority run on the main thread.

![[Pasted image 20220629125652.png]]
![[Pasted image 20220629125720.png]]

**.2** `.userInitiated`
The second highest priority and unlike the first this is used to execute tasks initiated on the user that yield results. ui that returns a result 

![[Pasted image 20220629125811.png]]
![[Pasted image 20220629125949.png]]

**.3** `.default`
the system defaults  to this when the user doesn't specify anything 
![[Pasted image 20220629130028.png]]

**.4** `Utility`
Used when you have tasks that don't prevent the user from continuing and that the user is willing to wait for. Such as calling a API
![[Pasted image 20220629130155.png]]

**.5**`.background`
these are the slowest tasks and one that the user is oblivious of such as data base related tasks.
![[Pasted image 20220629130321.png]]

## Custom queues
mostly executed on the global queue 
![[Pasted image 20220629130503.png]]
![[Pasted image 20220629130609.png]]
**Attributes**
in the absence of attribute the queue will run on a serial queue
![[Pasted image 20220629130724.png]]
![[Pasted image 20220629130539.png]]
![[Pasted image 20220629130739.png]]

`.initiallyInactive`
![[Pasted image 20220629131945.png]]

This is a custom queue that will not be executed until its activated
by calling its activated method. 

Comes in handy when you want to manually activate tasks. 
# What are async and sync programming 
these concepts come into effect when you have a complex app where your downloading and accessing data from api's at the same time the user is interacting with the data.

![[Pasted image 20220629205657.png]]
![[Pasted image 20220629205726.png]]

**Task Execution**
![[Pasted image 20220629205911.png]]

In iOS you can choose to dispatch different items synchronously or asynchronously where you have code executed on the main thread or done in order. using :
![[Pasted image 20220629210024.png]]

Sync code causes deadlocks 

## Dispatching asynchronously
running a task asynchronously  will start a task but will not wait for the task to be completed. 
Executions is returned immediately , tasks are FIFO but the first task isn't guaranteed to be the first one done. 

FIFO apply to when tasks start and note finish 
![[Pasted image 20220629210406.png]]
![[Pasted image 20220629210434.png]]

sync and or async are about waiting till another task is completed 
Concurrency has two tasks running at the same time but async has multiple methods in parallel on the same 1 thread.  
![[Pasted image 20220629210714.png]]

## Dispatching Synchronously
Sync programming is reliable and that becomes one of its greatest advantages. 
![[Pasted image 20220629210908.png]]

Comes in handy when :
 Example logging in 
![[Pasted image 20220629211006.png]]
![[Pasted image 20220629211016.png]]

**Benefits**
when the order of completion of a task is vital to the task then sync code comes in handy 
![[Pasted image 20220629211112.png]]

Calling sync might cause a deadlock and crash the users app 
![[Pasted image 20220629211126.png]]

**Code example**

The output will always remain the same over time and can only be changed by changing the order of the queue. 

Being able to run queue two before queue 3 

![[Pasted image 20220629211253.png]]


**Caching images**
Story board 

![[Pasted image 20220629211733.png]]

# Concurrency vs Parallelism 

**What are deadlocks**


![[Pasted image 20220629211854.png]]

sync will block the thread until the code is done executing  
![[Pasted image 20220629211917.png]]

The outer block is waiting for  the inner block to finish executing but the inner block cant execute until the outer block has executed. 
Causing a deadlock

![[Pasted image 20220629211958.png]]

**Avoiding Deadlocks**
![[Pasted image 20220629212136.png]]
![[Pasted image 20220629212154.png]]

![[Pasted image 20220629212310.png]]

![[Pasted image 20220629212206.png]]

![[Pasted image 20220629212318.png]]

**Code example**
Using Recursive locks 
![[Pasted image 20220629212502.png]]

using scheduler 

the scheduler will take a int 
print true or false if your subscribing from the main thread or the background thread 

we subscribe to the publisher by calling sink
and print by checking result 

![[Pasted image 20220629212829.png]]

**Deadlock example and solution**
![[Pasted image 20220629213010.png]]

Solution 
Making it a concurrent queue where you have the inner block not having to wait for the outer block to finish 
![[Pasted image 20220629212926.png]]

Making them both async
![[Pasted image 20220629212935.png]]

# Now what 
![[Pasted image 20220629213320.png]]
![[Pasted image 20220629213337.png]]
![[Pasted image 20220629213342.png]]