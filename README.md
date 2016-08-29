# About this repo 
I'm preparing myself for a whiteboard test.

I'm quite confortable with design patterns and object-oriented programming concepts so I will not document those. This document 
focuses on data structures and algorithms (DSA). 

I'm a front-end developer and I don't get to deal with complex data structures on daily basis. I need to try to remember these when 
I have a technical interview so I decided to document my preparation for the interview so it can save time to other developers 
preparing for a technical interview.

I hope you find this useful.

# Learning Resources
My two main learning resources are:

- [Data Structures and Algorithms: Annotated Reference with Examples](http://lib.mdp.ac.id/ebook/Karya%20Umum/Dsa.pdf) by Granville Barnett, and Luca Del Tongo
- [Cracking the Coding Interview: 189 Programming Questions and Solutions](http://amzn.to/2btJOH8) by Gayle Laakmann McDowell

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

![](bigo.png)

Consider trying a different data structure / algorithm if its performance is Quadratic, Cubic or Exponential.

If your algorithm uses a loop, it will be likely to have a linear performance O(n), if you use a loop inside a loop (e.g. traverse a 2D matrix) it will be likely to a quadratic performance O(n^2).

# Data Structures

## Singly linked list
Each node contains a reference to the next node in the list.
To improve performance it is recommended to keep a reference to the first node in the list (head) and the last node in the list (tail).

![](singly-linked-list.png)

Linked list are good for dynamic resizing and have a constant O(1) performance for head or tail insertion and deletion.

- Insertion in head or tail O(1)
- Insertion between head and tail O(n)
- Deletion head or tail  O(1)
- Deletion between head and tail O(n)
- Searching O(n)
- Traversing O(n)
- Reverse traversal O(n^2)

## Double linked list
TODO

# Algorithms
TODO

# Questions & Answers
TODO
