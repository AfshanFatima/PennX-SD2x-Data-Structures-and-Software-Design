# Week 1 Core Data Structures

**Motivating the need for Data Structures**

**Problem 1**

Which of the following is NOT a limitation of an array?

Adding an element to the front of an array can be time consuming.

Replacing an element at a specified index of the array can be time consuming. -correct.

We need to specify the size of the array ahead of time.

Checking whether an element is contained in the array can be time consuming.

Answer
Correct: In an array, we can always replace an element at a specified index regardless of where it is in the array. But because arrays are fixed size, adding an element to the front requires shifting all other elements. And since we don’t know the order of the elements, checking whether an element is contained may require inspecting every single element in the array.

**Problem 2**

We demonstrated the difficulty of inserting an element at the front of an array. Of the following options, which of these operations would NOT take, in the worst case, the same amount of time?

Replacing a specific element in the array given its value but not its index.

Accessing the element at a given index in the array. -correct.

Re-sizing the array.

Removing an element from the array.

Answer
Correct: Accessing an element at a given index can be done instantaneously, since we know exactly where it is with respect to the start of the array. But all of these other operations may in the worst case require inspecting or moving every element in the array.

**Problem 3**

Suppose we used an int array arr of size N+1 to keep track of the frequency with which we have seen a given number in the interval [0 … N]. That is, arr[i] = x if we have seen number i a total of x times so far. What limitation of arrays should we still be concerned about in this specific context?

We cannot easily insert an element in front of others.

Checking whether an array contains a number can be time consuming.

The array may be too large (wasted space). -correct

All of the above.

Answer
Correct: For all values i that we have never seen, arr[i] will be 0; it might be better to only keep track of the values that we have actually seen.

**Introduction to Linked Lists**

**Problem 1**

Suppose we wanted to create a function that replaces the first element in a linked list. Does the code below fulfill the intended function? If not, how should we correct it? 
![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/7dc1950019ebf9e1eb9dca6a706068ec/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-1.PNG)


The code is correct.

After line 2, add newNode.next = head.next; -correct

After line 3 add newNode.next = head.next;

Return the old head after line 3.

Answer
Correct: We need to set the newNode’s “next” field to refer to whatever was originally following the head of the linked list, and this needs to be done after line 2. If we wait until after line 3, it will be too late and we will have lost the original value of head.next.

**Problem 2**


When inserting a new node at a specified index of a linked list, what node must you have access to (in addition to the node you want to insert)?

Tail.

Node after the index.

Node at the index.

Node before the index. -correct

Explanation:
When inserting a node at a given index, we need access to the element before that index so that we can update its “next” field to refer to the newly added node.

**Linked List Operations**

**Problem 1**

![code snippet](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/67fd9e3d94ceb285575db0cabbad11b1/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-2.PNG)

Above is the contains function we presented in this lesson. Say we had a circular linked list. That is, we only need to keep track of a head node, and what was originally our tail node no longer points to null—it points to the head. What is one way we could change our implementation of contains to accommodate this change?

Update line 3 to check for current != head.

Replace the while loop with a do-while loop that checks for current != head. -correct

Add a check for current == head above line 7 and break if this is true.

No change.

Answer
Correct: We should not check whether current == head until after we have had a chance to update it on line 7. Therefore, a do-while loop would be the best solution so that we can at least compare one element and update “current” before performing the check.


**Removing elements from Linked Lists**

**Problem 1**

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/6aa8fe471a93611f51fd0844ae83ec7e/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-3.PNG)

Above is the implementation of removeFromFront we showed in this lesson. What would be an equivalent implementation of this function?

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/150d5f9164a4b9b433b38462b70228da/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-4.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/abff5c8e47df0194339603d6a6521e0d/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-5.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/b574b9ad1d6968bf9ca263452d8fdcb4/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-6.PNG) -correct 


![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/0b2b3cccc571f8885ee550c45940b9a0/asset-v1:PennX+SD2x+2T2017+type@asset+block/1-7.PNG)

Answer
Correct: We need to make sure that we update both head and tail if the list only has one element, but we also must check that there are elements before updating either.

**Problem 2**

If head is a reference to the first node of a linked list that has two or more elements, what happens when this operation is run? head = head.next;

Copies the node after head and adds it to the front of the linked list.

Removes the first node of the linked list. -correct

Removes the second node of the linked list.

Removes the whole linked list.

Answer
Correct: In this case, what was originally second in the list (i.e., following the head) is now at the front of the list, meaning that the first node is removed since it can no longer be accessed via the head of the linked list.

**Problem 2**

If head is a reference to the first node of a linked list that has two or more elements, what happens when this operation is run? head = head.next;

Copies the node after head and adds it to the front of the linked list.

Removes the first node of the linked list. -correct

Removes the second node of the linked list.

Removes the whole linked list.

Answer
Correct: In this case, what was originally second in the list (i.e., following the head) is now at the front of the list, meaning that the first node is removed since it can no longer be accessed via the head of the linked list.

**Problem 3**

If head is a reference to the first node of a linked list that has two or more elements, what happens when this operation is run? head = tail;

Removes all nodes from the linked list except the last element. -correct

Removes all nodes from the linked list.

Removes the first node of the linked list.

Copies the node at tail and adds it to the front of the linked list.

Answer
Correct: This means that whatever was the tail is also now the head of the linked list; therefore it is the only element and all other elements are removed, since they can no longer be accessed by the head of the linked list.

**Linked List and Array Lists in the Java API**

**Problem 1**

Which of the following is FALSE?

The ArrayList data structure internally uses an array.

A LinkedList will take up more space than an ArrayList.
Insertion and removal are faster in an ArrayList than in a regular array. -correct

Adding an element to the front of a LinkedList is faster than adding an element to the front of an ArrayList.

Explanation:
An ArrayList is simply an object that “wraps” or provides extra functionality to an array, but otherwise it still works the same.

 
**Problem 2**

Choose the Java data structure best suited for this application, given what you know about its available methods and their time/space efficiencies: I want to store the heights of k plants, each labeled numerically from 0 to k-1. I will measure all plants once per week and update their heights accordingly, and k will not change.

List

ArrayList.

LinkedList.

Array. -correct

Explanation:
An array is best here because we know the number of elements and we can use each plant’s label as the index.

 
**Problem 3**

Which of the following is TRUE?

LinkedList and ArrayList both implement the List interface, which extends the Collection interface. -correct

LinkedList and ArrayList both extend the List class, which extends the Collection class.

LinkedList and ArrayList both extend the List class, which implements the Collection interface.

LinkedLists and ArrayLists do not have Iterators. Only Collections have Iterators.

Answer
Correct: In Java, List is an interface, not a class. This means that we can have different types of Lists, but we cannot create an object that is simply a “List.” Since Lists are Collections, and LinkedLists and ArrayLists are Lists, they also have Iterators.

**Abstract Data Types**

**Queues and Stacks**

Problem 1

Which of the following statements about abstract data types is FALSE?

A stack is an example of an abstract data type.

A linked list is an example of an abstract data type. -correct

An abstract data type is a data type whose properties (data and operations) are specified independently of any one implementation.
A user only needs to know about its operations and any specified constraints on those operations.

Answer
Correct: Linked lists are not abstract data types because their implementation details are specified. Lists, however, can be considered abstract data types.

**Problem 2**

Which of the following is a valid linked list implementation of a queue?

Append items to the back of the linked list as they come in and remove starting from the tail.

Append items to the back of the linked list as they come in and remove starting from the head.

Append items to the front of the linked list as they come in and remove starting from the tail. 

Options 2 and 3 are equivalent. -correct

Explanation:
Option #1 defines a stack. Option #2 is the definition we saw in the lesson, but Option #3 is equivalent, just the other way around.

 
**Problem 3**

Which of the following statements about stacks and queues is TRUE?

A stack does not need to be implemented using a linked list, but a queue must be.

A queue does not need to be implemented using a linked list, but a stack must be. 

A stack needs pointers to both ends of the underlying structure, while a queue only needs one.

A queue needs pointers to both ends of the underlying structure, while a stack only needs one. -correct

Explanation:
Neither stacks nor queues necessarily need to be implemented using linked lists; they could certainly be implemented with ArrayLists or even arrays. However, a queue does need references to both the front and back, whereas the stack only has a “top.”

**Hash Sets**

**Comparing  Lists with Big-O Notation**

Problem 1

What would be the best and worst case run times for adding an element to an array list?

Best: O(n), Worst: O(1)

Best: O(1), Worst: O(n) -correct

Always O(1)

Always O(n)

Explanation:
In the worst case, we would either be adding an element to the front and then have to shift all other elements one-by-one; or we would try to add to an underlying array that is already full and then need to grow/resize the array. In the best case, though, we just add to the end of the underlying array.

**Problem 2**

What would be the best and worse case run times for getting an element by index in an array list?

Best: O(n), Worst: O(1)

Best: O(1), Worst: O(n)

Always O(1) -correct

Always O(n)

Answer
Correct: Because an ArrayList is just a wrapper around an underlying array, we can get elements by their index in O(1) or “constant” time because we know exactly where the element is with respect to the start of the array.

**Introduction to Hash Sets**

**Problem 1**

Which of the following is FALSE about the implementation of a hash set described in the lesson?
Elements are stored in an array.

Searching for an element is O(1).

Adding an element is O(1).

An element’s position in the array determines its hash code. -correct

Answer
Correct: In the implementation we’ve seen, each element is stored in an array and its index is determined based on its value.



**Problem 2**

Which of the following statements is TRUE?

A hash set orders elements in the same way an array does because it is implemented using an array.

We could implement a hash set using a linked list instead of an array and all operations would have the same time complexity.

Getting an element by its index in an array list is just as fast as finding an element in a hash set. -correct

None of the above.

Answer
Correct: The ordering of the elements in the hash set is determined by their values and not by the order in which they were added, which would be the case for an array. If were to use a linked list, operations would actually be slower because getting an element by its index is O(n), not O(1). Option #3 is correct because both operations are O(1).

**Problem 3**

What is NOT a shortcoming of our current hash set implementation?

It is a fixed size.

We cannot add multiple elements with the same hash code, even if their values are different.

Finding an element in the hash set requires inspecting all elements. -correct

All of the above.

Explanation:
In our current implementation, we have a fixed size array and only allow for one element to be placed in each array location, so those are limitations. However, Option #3 is not a limitation because finding an element is O(1), and is not affected by the number of elements.

**Hash Set Collision handling**

**Problem 1**

“Collision” in a hash set occurs when:

When there are more buckets than elements in the hash set.

Two elements have the same hash code. -correct

The hash code is larger than the size of the hash set.

When someone tries to insert the same element into the hash set twice.

Answer
Correct: Collision means that there are two or more elements that need to go into the same bucket. This can happen when they have the same hash code.

**Problem 2**

Given a hash set of n buckets, if there are k elements in a bucket b, and you are searching for an element with hash code b, what is the time complexity of that specific operation?

O(1)

O(n)

O(n * k)

O(k) -correct

Answer
Correct: In the worst case we would need to inspect all k elements in bucket b.

**Self-resizing Hash Sets**

Problem 1

If we initialized a hash set to have a load factor of 0.85 and an initial number of buckets to be 10, at what point would you need to resize the hash set?

When adding the 9th element. -correct

When adding the 12th element.

When adding the 13th element.

When adding the 1st element.

Answer
Correct: At this point, the load would be 9/10, which is greater than 0.85, so at that point the hash set would need to be resized.

**Problem 2**

Consider a reinsertAll implementation that doubles the number of buckets in the underlying array and copies over the linked lists from the old buckets. What is wrong with this implementation?

I should only add loadFactor * numBuckets to the size of the hash set, not double.

I should not need to copy anything over.

I should recompute the hash code for all of my elements based on the new number of buckets before adding them back into the array of linked lists. -correct

Answer
Correct: It is important that all elements in the old buckets be placed into the proper buckets in the new hash set. Hopefully by doing this, the number of elements in each bucket will be reduced and operations will become faster.

**Problem 3**


If the hash set were not resizable, what problem would occur?

Adding to the hash set would get slower.

Checking for an element in the hash set would get slower. -correct

Computing the hash code for an element would get slower.

All of the above.

Answer
Correct: If the hash set always stayed the same time, the buckets could have many elements, thus reducing the data structure to a linked list, for which operations are O(n) and not O(1), which is what we want.

**Hash Sets and Maps in the Java API**

**Problem 1**

What do HashSets and ArrayLists have in common?

Determining whether they contain an element is O(1).

Both have a load factor.

Both are self-resizing. -correct

None of the above.

Answer
Correct: HashSets automatically resize when the number of elements exceeds the load factor; ArrayLists resize when the number of elements exceeds the size of the underlying array.

**Problem 2**

Select the situation in which a HashMap should be used.

Checking whether or not a user has visited a web page before.

Designing a system that handles requests from multiple users (first-come-first-serve).

Storing the usernames of people who have made a certain request—no duplicates.

Storing the usernames of people who have made a certain request—no duplicates—and the number of times they have made this request -correct

Explanation:
A HashMap allows us to map a key to a value. In this case, the key would be the (unique) username and the value would be the number of times they have made the request.


**Problem 3**


What is the relationship between HashMap and Map?

Map and HashMap are two different classes with the same methods but different underlying implementations.

HashMap defines methods that Map implements.

HashMap implements methods defined in Map, in addition to methods specific to a HashMap.-correct

HashMap only implements methods defined in Map.

Answer
Correct: Map is an interface and HashMap is a class that implements it, but it also has its own methods.






