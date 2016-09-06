# About this document 
I'm preparing myself for a whiteboard test. I'm a front-end developer and I don't get to deal with complex data structures on daily basis. I need to try to remember these when I have a technical interview so I decided to document my preparation for the interview so it can save time to other developers  preparing for a technical interview.

Whiteboard tests usualy cover topics like:

- Data structures and algorithms (DSA).
- Object-oriented principles and design.
- System design principles.

This document focuses on data structures and algorithms (DSA). I'm quite confortable with design patterns and object-oriented programming concepts and I have limited time so I will not document those. If you need help to prepare your system design architecture you can refer to the open source [system design interview](https://github.com/checkcheckzz/system-design-interview) guide available on github.


I hope that other developers will find this guide useful when preparing for a technical interview.

You can read it online or [download this document as a PDF](https://github.com/remojansen/DSA/raw/master/pdf.pdf).

# Learning Resources
My main learning resources are:

- [Data Structures and Algorithms: Annotated Reference with Examples](http://lib.mdp.ac.id/ebook/Karya%20Umum/Dsa.pdf) by Granville Barnett, and Luca Del Tongo
- [Cracking the Coding Interview: 189 Programming Questions and Solutions](http://amzn.to/2btJOH8) by Gayle Laakmann McDowell
- [Big-O Cheat Sheet](http://bigocheatsheet.com/) by Eric Rowell

# Big O notation
Some of the most common Big O notations include:

- O(1) Constant
- O(log n) Logarithmic
- O(n) Linear
- O(n log n) Log linear
- O(n^2) Quadratic
- O(n^3) Cubic
- O(n^n) Exponential


The following diagram represent the preceding Big O notations:

- The X axis to represents the number of items (n) in the data structure.
- The Y axis represents the time (O) required to perform an operation.

<img src="bigo.png" width="650" />

Consider trying a different data structure / algorithm if its performance is Quadratic, Cubic or Exponential.

If your algorithm uses a loop, it will be likely to have a linear performance O(n), if you use a loop inside a loop (e.g. traverse a 2D matrix) it will be likely to a quadratic performance O(n^2).

# Data Structures

## Stack
Stack is an ordered list of similar data type. Stack is a LIFO structure. Both insertion and deletion are allowed at only one end of Stack called Top.

<img src="stack.png" width="500" />

An stack is good when you need to "do" and "undo" something. Many parsing problems (e.g validate blocks properly closed in a programming language) can be solved using a stack.

- Insertion in head or tail O(1)
- Deletion head or tail  O(1)
- Searching O(n)
- Traversing O(n)

## Singly linked list
Each node contains a reference to the next node in the list.
To improve performance it is recommended to keep a reference to the first node in the list (head) and the last node in the list (tail).

![](singly-linked-list.png)

Singly linked list are good for dynamic resizing and have a constant O(1) performance for head or tail insertion and deletion.

- Insertion in head or tail O(1)
- Insertion between head and tail O(n)
- Deletion head or tail  O(1)
- Deletion between head and tail O(n)
- Searching O(n)
- Traversing O(n)
- Reverse traversal O(n^2)

## Doubly linked list
Each node contains a reference to the next and previous nodes in the list.
To improve performance it is recommended to keep a reference to the first node in the list (head) and the last node in the list (tail).

![](doubly-linked-list.png)

Doubly linked list are good for dynamic resizing, have a constant O(1) performance for head or tail insertion and deletion and have a better O(n) for reverse traversal operations than singly linked lists O(n^2).

- Insertion in head or tail O(1)
- Insertion between head and tail O(n)
- Deletion head or tail  O(1)
- Deletion between head and tail O(n)
- Searching O(n)
- Traversing O(n)
- Reverse traversal O(n)

Singly and doubly linked list are a good option when you know that you will insert, read or delete from the head or tail of the list. However, they are not a good option when searching, accesing by index or inserting between the tail and head nodes.

## Circular linked list
Another method of implementing a linked list (singly or doubly linked) involves using a circular form so that the last node points back to the first node.

![](circularlist.png)

Circular data structure would be more natural when used to represent circular problems (e.g turns in card game).
Circular linked List allow us to traverse the entire list starting from any node and allow as to think about fewer 
special cases when coding (all nodes have a node before and after it). 

However, finding end of list and loop control is harder (no NULL's to mark beginning and end). 

Another problem is that if we point to the start of the list and we want to add/remove an item to the front, we would need to go through the entire list in order to find the last node so that we could keep the linked list hooked up properly. The solution to this problem is to forget about the head reference entirely and just have a tail reference (if we point to just the tail node, it is very very easy to find out the gead node).

- Insertion in head or tail O(1)
- Insertion between head and tail O(n)
- Deletion head or tail  O(1)
- Deletion between head and tail O(n)
- Searching O(n)
- Traversing O(n)
- Reverse traversal O(n)

## Binary Search Tree (BST)
Binary search trees (BSTs) start with a root node with value x, where the left subtree of x contains nodes with values < x
and the right subtree contains nodes whose values are ≥ x. 

Each node follows the same rules with respect to nodes in their left and right subtrees

![](bst.png)

BSTs are of interest because insertion, search, and deletion can all be done in O(log n) time. It is important
to note that the O(log n) times for these operations can only be attained if the BST is reasonably balanced (a pathologically unbalanced tree become linear and  is effectively just a linked list).

- Insertion O(log n)
- Deletion O(log n)
- Searching O(log n)
- Traversing (Preorder, Postorder, Inorder & Breadth first) O(n)

### BST Deletion
Inserting and searching for a node is very simple but removing an element is not straight forward and requires to consider 3 cases:

- If the node to be removed has no children (leaf node) we just simply remove it.
- Node to be removed has one child. It this case, node is cut from the tree and algorithm links single child (with it's subtree) directly to the parent of the removed node.
- Node to be removed has two children. In this case we need to find the minimum value in the right subtree. Replace value of the node to be removed with found minimum. 
Now, right subtree contains a duplicate! Apply remove to the right subtree to remove a duplicate.

![](bst_deletion.png)

### Preorder BST traversal
Then traverse the left subtree and finally traverse the right subtree.

![](bst_preorder.png)

### Postorder BST traversal
The value of the node is yielded after traversing both subtrees.

![](bst_postorder.png)

### Inorder BST traversal
The value of the current node is yielded in between traversing the left subtree and the right subtree

![](bst_inorder.png)

### Breadth first BST traversal
Traversing a tree in breadth first order yields the values of all nodes of a particular depth in the tree before any deeper ones.

![](bst_breadth_first.png)

## Queue
A queue is an ordered list that keeps a reference to its head and tail. The queue is a FIFO structure.
The main difference between a linked list and a queue is that the queue only allow us to add items to 
its tail and remove items from its head.

![](queue.jpg)

- Insertion in tail O(1)
- Deletion in head O(1)
- Searching O(n)
- Traversing O(n)

Priority queues insert elements in a position based on its priority level. Some implementations of
priority queue use a heap data structure under the hood so its execution tames are the same as a 
standard queue.

## Heap
A heap is a specialized tree-based data structure that satisfies the heap property. If A is a parent node of B 
then the key (the value) of node A is ordered with respect to the key of node B with the same ordering applying 
across the heap.

The heap can follow two strategies:

- Min heap: each parent node would have a value that is <= than its children.
- Max heap: each parent node would have a value that is > than its children.

Heaps are most commonly used to implement priority queues and to facilitate heap sort.

Unlike other tree data structures a heap is generally implemented as an array rather 
than a series of nodes which each have references to other nodes. 

The nodes are conceptually the same, however, having at most two children.

The following figure shows how the tree (not a heap data structure) would be represented as an array.

![](tree-as-array.png)

The following figure shows how we could implement adding elements to a heap:

![](heap-inserting.png)

There are multiple possible implementations of heaps with different execution times. 
For example, a fibonacci heap has a better running time than many other priority queue data structures 
including the binary heap and binomial heap.

![](heap-big-o.png)

## Sets
TODO

## Hash table
TODO

## Self-balancing binary search tree (AVL Tree)
TODO

## Graphs
TODO

# Algorithms
TODO

# Questions & Answers
Here you can find some DSA interview questions.

## Implement a Fibonacci sequence using recursive and sequentialal gorithms

The pattern of the Fibonacci sequence is that each value is the sum of the 2 previous values:

```
F(n) = F(n-1) + F(n-2)
```

Sequential (Basic) O(n):

```js
function fibonacci(num){
  var a = 1, b = 0, temp;

  while (num >= 0){
    temp = a;
    a = a + b;
    b = temp;
    num--;
  }

  return b;
}
```

Sequential (Optimized via Memoization) O(2*n):

```js
function fibonacci(num, memo) {
  memo = memo || {};

  if (memo[num]) return memo[num];
  if (num <= 1) return 1;

  return memo[num] = fibonacci(num - 1, memo) + fibonacci(num - 2, memo);
}
```

Recuersive O(2^n):

```js
function fibonacci(num) {
  if (num <= 1) return 1;

  return fibonacci(num - 1) + fibonacci(num - 2);
}
```

TODO
