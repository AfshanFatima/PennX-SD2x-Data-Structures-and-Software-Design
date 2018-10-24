# Week 4 Implementing and Improving Software

**Making Code Easier to Understand**

**Analyzability**

**Problem 1**

Making code easier to read also makes it easier to:

understand

change

test and debug

all of the above -correct

Answer
Correct: Improving the visual appearance of the code and making it easier for someone to differentiate the tokens helps make it easier to understand, which in turn improves its internal quality.

**Problem 2**

I have a variable of type List which I am using to represent the items that a user has purchased. From an understandability perspective, the best name for this variable is:

list

items

purchasedItems -correct

allItems

Answer
Correct: Although longest, “purchasedItems” is most descriptive in that it distinguishes this from items in general.

**Problem 3**

The structural complexity of a method refers to:

the number of decision points in the code -correct

the number of variables used in the code

the use of while-loops instead of for-loops

the number of reachable statements in the code'

Answer
Correct: Structural complexity is related to the “structure” of the code in terms of its control flow, which is affected by decision points: if-statements, loops, etc.

**Refactoring**

**Problem 1**

The goal of refactoring is to:

make code easier to understand

make code easier to change

make code easier to test and debug

all of the above -correct

Answer
Correct: Refactoring is meant to improve all aspects of internal quality.

**Problem 2**

I have a public method named “read” that reads the contents of a file, and decide to change it to “readFile” in order to make it more descriptive. What is a negative side effect of this refactoring?

any code that uses that method now has to be changed -correct

the modularity of my code has decreased

the functional independence of my code has decreased

all of the above

Answer
Correct: It is true that code that depends on my method now has to be changed, but aspects of internal quality are not affected by this refactoring.

**Addressing duplicate code**

**Problem 1**

The “duplicate code” code smell is a problem because:

a change in one part of the code necessitates change elsewhere

there are more places to modify the code if it needs to be changed -correct

it makes the code slower

it hurts abstraction

Answer
Correct: Duplicate Code is primarily a problem with changeability, as well as understandability and testability, though not necessarily stability (Option #1) or any aspect of external quality (Option #3).

**Problem 2**

I have a design in which duplicate code is found in classes A and B. Using the Extract Superclass refactoring pattern, I would:

have A and B extend a new class C and then move the common code to C -correct

have A extend B and put the common code in B

put the common code in a new class C and make C a field in both classes A and B

put the common code in B and have it be a field in class A

Answer
Correct: In the Extract Superclass pattern, we create a new parent class that holds any duplicate code, and then classes can extend that class in order to inherit the common functionality

**Problem 3**

A potential challenge/problem with applying the Extract Method refactoring pattern in Java is:

the newly created method may need to take many arguments

the newly created method may need to have many return values -correct

the code from which the method is extracted becomes shorter

the code becomes harder to read

Answer
Correct: It is okay for the new method to take many arguments, but if it has many return values, that would require some sort of workaround in a language like Java. The other two options are both true, but desirable!

**Addressing large classes and long methods**

**Problem 1**

I have a “large class” code smell and address it using the Extract Class refactoring pattern. What sort of relationship do I create between the two classes?

aggregation/composition -correct

generalization

realization

dependency

Answer
Correct: The Extract Class pattern creates a “has-a” relationship between the two classes. This can either be aggregation or composition.

**Problem 2**

The “large class” code smell is primarily a problem with which aspect of software design?

modularity -correct

functional independence

abstraction

reliability

Explanation:
When a class is too large, we would try to break it into smaller pieces, thus making it more modular.


**Problem 3**

You are developing a human resources management system and have a class Employee which is getting to be too large. To refactor it, you should:

apply the Extract Class pattern: move some general fields/methods into a class Person and create a “has-a” relationship between Employee and Person

apply the Extract Class pattern: move some general fields/methods into a class Person and create a “has-a” relationship between Person and Employee

apply the Extract Superclass pattern: move some general fields/methods into a class Person and create an “is-a” relationship between Employee and Person -correct

apply the Extract Superclass pattern: move some general fields/methods into a class Person and create an “is-a” relationship between Person and Employee

Answer
Correct: Since an Employee “is a” Person, the Extract Superclass pattern would be best, with Employee extending Person.

**Making Code more  Reliable**

**Reliability**

**Problem 1**

Defensive programming is what kind of technique for improving reliability?

fault prevention

fault removal

fault tolerance -correct

fault avoidance

Answer
Correct: “Fault tolerance” means that even though there are problems in the code – either ours or someone else’s – the code keeps running. Defensive programming allows us to accomplish this by looking for problems and dealing with them.

**Problem 2**

Instead of using exceptions, we should use Java assertion statements in our code when we’re looking for:

potential problems that may come from an unrecoverable bug in our code -correct

unexpected inputs from code that is using our code

unexpected return values coming from code that we are using

all of the above

Answer
Correct: We should not use assertions to check for unexpected inputs or return values, because, if violated, they would lead to AssertionErrors, which are unlikely to be caught and would crash the program. However, when we detect a bug in our code and cannot recover from it, an assertion would be appropriate as it represents a state that should never happen.

**Making Code More Efficient**

**Efficiency  part 1**

**Problem 1**

Using a LinkedList is likely to be much, much slower than using an ArrayList when:

we are repeatedly searching to see whether it contains a given element

we are repeatedly adding elements

we are repeatedly removing elements

we are repeatedly accessing elements by their index -correct

Explanation:
Remember, accessing an element by its index is O(1) in an ArrayList, but O(n) in a LinkedList. This can have a major effect on efficiency if the list is very large.

 
**Problem 2**

A TreeSet would be faster than a HashSet in the situation when:

elements are added in their natural order

there are more remove operations than add operations

all elements have the same hash code -correct

none of the above

Answer
Correct: If all elements have the same hash code, then they will all go into the same bucket in a HashSet, meaning it is essentially a LinkedList and operations will be O(n). In the other cases, though, a HashSet will be faster.

**Efficiency part 2**

**Problem 1**

In terms of improving efficiency, the suggestion “don’t use exceptions unnecessarily” comes from the fact that:

Exceptions are objects that need to be created -correct

checking to see whether values are valid is a waste of time

exception handling makes the code harder to understand

assertions are faster than exceptions

Answer
Correct: In many cases, it is faster to perform a check and handle it than to wait for Java to handle the exception, primarily because Exceptions are objects.

**Problem 2**

I am writing an if-statement using methods “fast” and “slow,” for which “fast” on average executes twice as quickly as “slow.” Which of the following would, on average, be fastest?

if (fast() && slow())

if (slow() && fast())

if (!(!fast() || !slow())) 

it depends on how likely each is to return true -correct

Explanation:
It is tempting to say Option #1 because we want to do the fast one first, but if “fast” returns true a large majority of the time, then we would almost always execute “slow” anyway. If “slow” generally returns false, it may make more sense to put it first, so that the short-circuit “and” operator would return false and not bother executing “fast.”

**Problem 3**

Which of the following is NOT assumed when using memoization to improve the execution time of a particular method?

The method is deterministic, i.e. always returns the same result for the same input.

The overhead of storing/retrieving the memoized results is less than the time it takes to compute them.

The method will be called with the same input more than once.

The method takes a single parameter. -correct

Answer
Correct: Memoization can be used even when the method takes multiple parameters, as long as they can be combined into some unique key for the map. Although memoization does assume all those other things, it can greatly improve efficiency if they’re all true!

**Using threads in Java**

**Problem 1**

I have a class MyRunnable that implements the Runnable interface and want to start executing it in a new thread. The code that will do this is:

new MyRunnable().run();

new MyRunnable().start();

Thread.start(new MyRunnable()); 

new Thread(new MyRunnable()).start(); -correct

Explanation:
If MyRunnable implements Runnable, we know that it will have a run method, but we should not invoke it if we want to start a new thread, as this will simply invoke that method in the current thread, just like any other method. The class may not have a start method, which is what we need, so we would need to pass an instance of the object to a new Thread object, and then call its start method.

**Problem 2**

I have a class AdderThread that extends Thread, and its “run” method finds the sum of the elements of an array; the sum can then be retrieved by the “getSum” method. The following code tries to use the AdderThread class but always returns 0. How can I fix the problem so that I still take advantage of threads? 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/bf98b66d283e8a74916f9da5dcef5f5a/asset-v1:PennX+SD2x+2T2017+type@asset+block/4-1.PNG)

put t1.join() between lines 4 and 5, and t2.join() between lines 5 and 6

put t1.join() and t2.join() between lines 5 and 6 -correct

change lines 4 and 5 to t1.run() and t2.run()

omit lines 4 and 5 

Explanation:
The problem is that we are not using waiting for the “run” methods to finish, but rather are calling getSum on line 6 before it is done. Options #1 and #3 would work, but would make the code sequential: in each case, it would wait for t1 to finish before proceeding to t2. We should put the join statements after the start statements, so that we wait for each thread to finish before executing line 6.

**Thread race Conditions**

**Problem 1**

In the code below, which of the following might lead to a race condition if Threads A and B are sharing the same instance of MyClass? 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/623f532d34ed9f3c4588cb08c27bb6bb/asset-v1:PennX+SD2x+2T2017+type@asset+block/4-2.PNG)

Thread A executes line 5 while thread B executes line 6

Thread A executes line 6 while thread B executes line 6

Thread A executes line 4 while thread B executes line 5

None of the above -correct

Explanation:
Because “local” is a local variable and “param” is a method parameter, each thread has its own copy, so there is no possibility that one thread can affect the other. The only possible variable on which there could be a race condition is “global,” but it is not modified here.

**Problem 2**

I have a class that extends Thread defined as follows: 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/bf3e7595d373d1f171048abe92c62614/asset-v1:PennX+SD2x+2T2017+type@asset+block/4-31.PNG)

I am then using it in this code:

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/de5cf81f418abe03919e114f479d3e6f/asset-v1:PennX+SD2x+2T2017+type@asset+block/4-32.PNG)

What might be printed on the last line of the above code?

0 or 1 only

1 or 2 only -correct

2 only 

0, 1, or 2

Explanation:
The code will definitely not print 0, since at least one of the threads will successfully increment the value before join is called. We expect it to print 2, but it might also print 1. For instance, thread A starts to increment the variable "value", reading the initial value of 0, and A is interrupted by the other thread B that wants to increase it. Thread B still reads the original value of 0. Thread A finishes and update "value" to be 1 and then, hread B finishes calculating and update the "value" to be a final value of 1.

**Synchronization in Java**

**Problem 1**

I have the following class and am worried about race conditions: 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/ad4b05fbc6be75d0838541f538e35875/asset-v1:PennX+SD2x+2T2017+type@asset+block/4-4.PNG)

In order to avoid race conditions, I should:

make “deposit” a synchronized method -correct

make “getBalance” a synchronized method

make “balance” a synchronized field

all of the above 

Explanation:
As we saw in the lesson, “deposit” should be synchronized so that only one thread at a time can execute it. There is no need for “getBalance” to be synchronized because there is no possibility of a race condition there. And there’s no such thing as a synchronized field in Java!

**Problem 2**

How could a race condition exist in the following code, assuming the method calls are on the same object? 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/0a514270a593036ebbdce63934e292d9/asset-v1:PennX+SD2x+2T2017+type@asset+block/4-5.PNG)

One thread calls updateValue1 while another calls updateValue2

One thread calls updateValue2 while another calls updateBoth

One thread calls updateBoth while another calls updateBoth 

None of the above -correct

Explanation:
There are no race conditions in this code. There is no way for two threads to simultaneously update value1, because the updateValue1 method is synchronized, and updateBoth requires access to “this” object’s lock in order to update value1; however, if another thread is in a synchronized method, then “this” object’s lock is considered to be acquired. Likewise, the two lines on which value2 is updated are both protected by the “lock” object’s lock, so two threads cannot simultaneously update value2, either.
