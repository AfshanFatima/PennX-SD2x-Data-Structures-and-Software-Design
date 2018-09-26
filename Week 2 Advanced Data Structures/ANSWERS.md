# Week 2 Adanced Data Structures

**Binary Search Trees**

**Problem 1**

What is the problem with maintaining a sorted linked list?

Deleting from a sorted linked list will require re-sorting every time.

Adding to a sorted linked list is an O(n) operation. -correct

Traversing a sorted linked list is an O(n) operation.
None of the above.

Answer
Correct: In the worst case, we would have to put the newly inserted value toward the end of the list and compare it to all other elements, which would be O(n).

**Problem 2**

Which of the following is NOT specific to a binary search tree?

Each node has exactly two non-null child nodes. correct

Every node in the tree is greater than each element in its left subtree.

Every node in the tree is less than each element in its right subtree.

All of these are properties specific to a binary search tree.

Explanation:
A node may have non-null children, but is always greater than elements to its left and less than elements to its right.

**Problem 3**

An inorder traversal of a binary search tree:

Requires that we know the value of the leftmost node in the binary search tree.

Returns the node values in sorted order. -correct

Visits the root node, then the leftmost subtree, and then the rightmost subtree.

Visits the leftmost subtree, the rightmost subtree, and then the root.

Answer
Correct: Inorder traversal means “left, root, right” so we always get smaller values, then the value itself, then larger values. This means that the values will be sorted.

**Binary Search Tress Operations**

**Problem 1**

When searching for an element in the BST, when do we know for sure that the element is not contained in the tree?

When we have visited all elements in the BST.

When we have visited half of the elements in the BST.

When we have traversed the bottom-most level of the BST (the level farthest from the root).

When we have encountered a null node. -correct

Answer
Correct: Once we encounter a null, or “leaf,” node, then we know the value cannot be in the tree, otherwise we would have seen it already.

**Problem 2**

What sequence of add operations results in the following binary search tree? 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/1f9ecb1f98d2b4ee43a1f1eb626364ee/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-1.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/a4147a54e4e6743fa99d8ae606506690/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-2.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/30fd551d5119d1a66cffab64ee31ce1c/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-3.PNG)
-correct

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/e525e7b59632b0a770a0e70e95dad122/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-4.PNG)

Not possible

Answer
Correct: This is essentially a linked list and occurs when the values are inserted in increasing order.

**Problem 3**


Consider the following binary search tree: 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/d2cfe06a2725c773ca5d219168f77376/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-5.PNG)

What will the above tree look like after inserting a value 8?

Stay the same


![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/0794cb80cfe401ac2752d986fa311865/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-6.PNG)
-correct

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/14ab86abfa0d7476c25217b6212abaf5/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-7.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/2f137bca0e86ffbceb6ee9e21b9a5fd7/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-8.PNG)

Answer
Correct: Because 8 is smaller than 11, it will go to the left subtree. Because it is smaller than 9, it will go to its lefts.

**Removing  Elements From Binary Search Trees**

**Problem 1**

Based on our implementation of removing an element from a BST, what would the following tree look like after removing first 11 and then 14? 

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/06a80dbc3582652730b5775532ece7c8/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-9.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/4a89c2fb373c0e746194930d839fae16/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-10.PNG)-correct

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/2c666293b80d1eff377a0dd841320b30/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-11.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/9bc899df4d67a997cc88c68f57a4c76f/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-12.PNG)

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/b515bbf37f399e97ab27f4396eb504a4/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-13.PNG)

Answer
Correct: When we remove the 11, the 10 would take its place because it is the largest left child. Then when we remove the 14, the 20 would move up to its place.

**Self-Balancing Binary Search Trees**

**Problem 1**

What is the goal of a balanced binary search tree?

To color the nodes so that it is easy to visually distinguish different categories of nodes.

To have the same number of nodes in the left subtree and right subtree.

To make sure all levels of the tree that can be filled are filled.

To minimize the height of the tree. -correct

Answer
Correct: In order to maintain the O(log n) property, we need to make sure that the height is minimized, which is done by balancing the tree.

**Tree Sets in the  Java API**

**Problem 1**

Which of the following interfaces need to be implemented by elements that are to be stored in a TreeMap?

Comparable -correct

Iterator 

Map

Set

Explanation:
We need to be able to compare the elements in order to store them in sorted order, thus they must implement the Comparable interface.

**Problem 2**

![](https://prod-edxapp.edx-cdn.org/assets/courseware/v1/69d3283c310b2b3c1b04dae10467611c/asset-v1:PennX+SD2x+2T2017+type@asset+block/2-14.PNG)

What is the output of the above code?

banana apple watermelon peach

banana apple peach watermelon

peach apple banana watermelon

apple banana peach watermelon -correct

Answer
Correct: The elements will be printed in sorted order, regardless of the order in which they were added.

**Heaps**

**Problem 1**

In a max-heap implemented as a tree, where are new nodes inserted at the beginning of the algorithm to add a new element?

At the root of the tree.

At the next open location in the tree. -correct

At the correct sorted location within the tree.

At the location of the minimum value in the tree.

Answer
Correct: Elements to be added are placed at the next open location and then “bubble up” to the appropriate position. This makes sure that the heap stays balanced.

**Problem 2**

How many elements are in the bottom level of the following heap when represented in array form? 18 14 16 13 9 12 10 11 4 6 7 8

4

5 -correct

6

7

Answer
Correct: 18 is the root; 14 and 16 are its children; 13, 9, 12, and 10 are at the next level; and 11, 4, 6, 7, and 8 are at the bottom.

**Problem 3**

18 14 16 13 9 12 10 11 4 6 7 8

What will be the final configuration of the following max-heap in array form after adding 15?

18 15 16 13 14 12 10 11 4 6 7 8 9

18 14 16 13 9 12 15 11 4 6 7 8 10

18 14 16 13 9 12 10 11 4 6 7 8 15

18 14 16 13 9 15 10 11 4 6 7 8 12 -correct

Answer
Correct: The 15 will be placed at the end and then switched with its parent, which is 12. Then it will be compared to its new parent, which is 16; since it is not greater than 16, it will stay in its place.

**Removing Elements from Heap**

**Problem 1**

In a max-heap, which element takes the max element’s place after it’s been removed and the algorithm is finished?

The minimum value of the right subtree.

The left child.

The larger of its two children. -correct

The last element in the heap

Answer
Correct: This guarantees that the largest element is still at the top of the heap.

**Problem 2**

The Java PriorityQueue class implements a min-heap. How can we use it as a max-heap?

Pass in a maxHeap flag into the constructor.

Modify the compareTo function in our objects. -correct

Add elements to the Queue in order of importance.

Add elements to the Queue in order of least importance.

Answer
Correct: By switching the behavior of the compareTo method, we can make the minimum value appear as maximum (and vice-versa).

**Graphs**

**Problem 1**

We can think of a tree data structure as a directed graph in which there is an edge from a parent to each of its childen. Aside from the root node, the degree of each node in a binary search tree is:

Between 1-3 -correct

Between 0-3

Between 0-2

Between 2-3

Answer
Correct: A node can have up to two children, so a maximum out-degree of 2, but it also necessarily has a parent and thus an in-degree of 1. So the total is at least 1 and maximum 3.

**Problem 2**

Which of the following is NOT necessarily true of a cycle?

Is also a path.

Has the same first and last node.

Can be directed or undirected.

All nodes have edges to all other nodes. -correct

Explanation:
It is not necessary for the graph to be “fully connected,” i.e. that each node has edges to every other node.

**Problem 3**

Assume that s and d are nodes in directed graphs S and D, respectively, which are two strongly connected graphs that are separate from each other. Adding an edge from s to d would result in which of the following?

A single strongly connected graph.

We would be able to reach all nodes in D from any node in S but not the other way around. -correct

We would be able to reach all nodes in S from any node in D but not the other way around.

The out-degree of d would go up by 1.

Answer
Correct: This would mean that any node in S can get to s, which can get to d, which can get to any node in D. However, without an edge from d to s, the reverse is not true.

**Representing Graphs in Java**

**Problem 1**

If G is a directed, unweighted graph with 15 vertices and 20 edges, how many 0/1 values are needed to represent G in an adjacency matrix?

15

35

225 -correct

300

Answer
Correct: The number of edges is irrelevant in an adjacency matrix representation, but we would need 15x15 = 225 values to represent whether there are edges from each node to every other node.

**Problem 2**

Which of the following statements is TRUE about graph representations?

An adjacency matrix is always symmetric.

The edge set representation contains the same number of edges as the adjacency set representation. -correct

If a graph has many nodes and a small number of edges, it is better to use an adjacency matrix representation because it will take up less space.

In an adjacency set representation of a directed graph, an edge from node a to node b will be contained in both a’s adjacency set and b’s adjacency set.

Answer
Correct: An adjacency matrix is not necessarily symmetric in a directed graph, and the space it consumes is independent of the number of edges. However, it is true that both an edge set and adjacency set will represent the same number of edges, which would not change based on the representation.

**Graph Breadth-First Search**

**Problem 1**

BFS is implemented using a

Queue -correct

Map

Stack

Tree

Answer
Correct: In BFS, we keep add nodes to visit to the end of the data structure, since they are at the next level down in the tree. This can be done with a queue.

**Graph Depth-First Search**

**Problem 1**

Given 2 nodes in a graph, s and d, which of the two traversals, BFS and DFS, can I use to determine whether or not a path exists between the 2 nodes?

BFS

DFS

Neither

Both -correct

Answer
Correct: Although BFS will find the path with the smallest number of edges, DFS is also guaranteed to find a path as well.

**Problem 2**

A non-recursive implementation of DFS uses a

Queue

Map

Tree

Stack -correct

Answer
Correct: In DFS, nodes to visit are put at the front of the list, then visited, then their children are added to the front and so on. This would use a stack.

**Problem 3**

In an unweighted graph of n nodes and m edges, performing BFS from source node s to destination d always

Produces the shortest path from s to d. -correct

Visits n nodes when determining the path. 

Visits nodes in decreasing order of distance from the s to d.

Uses a queue to keep track of the edges it has traversed.


