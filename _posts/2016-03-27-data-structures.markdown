---
layout: post
title:  "Interviews: Data Structures"
date:   2016-03-27 01:00:00 -0800
categories: interviews
tags: interview data-structures
comments: true
---

This series contains review materials for software engineer interview practice. This guide provides a high-level overview on basic data structures including their implementations, related algorithms, and efficiency.


### **Arrays/Strings**

#### Overview:
- Stores data elements based on an sequential, most commonly 0 based, index.
- Based on [tuples](http://en.wikipedia.org/wiki/Tuple) from set theory.
  
#### Types:
- Optimal for indexing; bad at searching, inserting, and deleting (except at the end).
- **Linear arrays**, or one dimensional arrays, are the most basic.
  - Are static in size, meaning that they are declared with a fixed size.
- **Dynamic arrays** are like one dimensional arrays, but have reserved space for additional elements.
  - If a dynamic array is full, it copies it's contents to a larger array.
- **Two dimensional arrays** have x and y indices like a grid or nested arrays.  
  
#### Efficiency:
- Access:         O(1)  
- Search:         O(n)
- Sorted Search:  O(log n)
- Insertion:      O(1)
- Deletion:       O(n)


### **Stacks**

#### Overview:
- Collection of objects, typically supports *push* and *pop* operations
- Examines the item most recently added, **last in, first out** (LIFO) data structures.

#### Types:
- Commonly implemented with linked lists but can be made from arrays too.
- Made with a linked list by having the head be the only place for insertion and removal.
- Made with array by automatically resizing, **repeated doubling**

#### Efficiency:
- Access:     O(n)
- Search:     O(n)
- Insertion:  O(1)
- Deletion:   O(1)


### **Queue**

#### Overview:
- Collection of objects, typically supports *enqueue* and *dequeue* operations
- Examines the oldest item, **first in, first out** (FIFO) data structures.

#### Types:
- Commonly implemented with linked lists but can be made from arrays too.
- Made with a linked list by having the head be the only place for insertion and tail the only place for removal.
- Made with array by automatically resizing, **repeated doubling**
  - Head and tail indexes are incremented and decremented modulo the capacity

#### Efficiency:
- Access:     O(n)
- Search:     O(n)
- Insertion:  O(1)
- Deletion:   O(1)

### **Hash Table**

#### Overview: 
- Stores data with key value pairs.
- Designed to optimize searching, insertion, and deletion.
- **Hash functions** accept a key and return an output value unique to that specific key. 
  - Method for computing array index from key.
- **Hash collisions** are when a hash function returns the same output for two distinct outputs.
  - All hash functions have this problem.
  - This is often accommodated by creating large hash tables (arrays).

#### Types:
- There are a few different techniques for dealing with collision resolution
- **Separate chaining**
  - Use array of linked lists. When searching for key, check each entry of list associated with hash value.
  - Array size M must consider number of key-value pairs N. Typical choice M ~ N/5. 
    - The constant is equal to average number of constant time operations.
- **Open addressing**
  - When a new key collides, find next empty slot, and store it there.
  - Array size M must be larger than number of key-value pairs N. Typically N/M ~ 1/2.

#### Efficiency:
- Search:    O(1)
- Insertion: O(1)
- Deletion:  O(1)

### **Linked List**

#### Overview:
- Stores data with **nodes** that point to other nodes.
  - Nodes, at its most basic it has one datum and one reference (another node).
  - A linked list _chains_ nodes together by pointing one node's reference towards another node.
- List requires maintaining a reference to the head and/or tail node
- Designed to optimize insertion and deletion, slow at indexing and searching.

#### Types:
- **Singly linked list** has nodes that reference next node.
- **Doubly linked list** has nodes that reference the previous and next nodes.
- **Circularly linked list** is simple linked list whose **tail**, the last node, references the **head**, the first node.

#### Algorithms:
- **Runner**
  - Use two pointers to iterate through list
  - Increment at different rates to search for middle (p1 at 1x, p2 at 2x, p1 ends up in middle)

#### Efficiency:
- Access:     O(n)
- Search:     O(n)
- Insertion:  O(1)
- Deletion:   O(1)

 
### **Binary Tree**

#### Overview: 
- Is a tree like data structure where every node has at most two children (left and right).
- Designed to optimize searching and sorting.
- They are comparably simple to implement than other data structures.

#### Types:
- **Balanced tree** is a tree with minimum possible maximum height for all the leaf nodes.
  - Red-Black and AVL Trees are common implementations of balanced trees 
- **Degenerate tree** is an unbalanced tree, which if entirely one-sided is a essentially a linked list.
- **Complete tree** is a tree with all levels filled except possibly the last and all nodes are as far left as possible.
- **Binary search tree** is a tree that uses comparable keys to assign which direction a child is.
  - Left child has a key smaller than it's parent node.
  - Right child has a key greater than it's parent node.
  - There can be no duplicate node.
  - Because of the above it is more likely to be used as a data structure than a binary tree.

#### Algorithms:
- **Depth-First Search**
  - The search tree is deepened as much as possible on each child before going to the next sibling.
  - Typically implemented recursively using the stack
- **Depth-First Search Traversal Order**
  - Pre-Order: Root, Left, Right
  - In-Order: Left, Root, Right
  - Post-Order: Left, Right, Root
- **Breadth-First Search**
  - The search tree is broadened as much as possible on each depth before going to the next depth.
  - a.k.a level-order

#### Efficiency:
- Access:     O(log n)
- Search:     O(log n)
- Insertion:  O(log n)
- Deletion:   O(log n)


### **Tries**

#### Overview:
- Variant of an n-ary tree in which characters are stored at each node.
- Each path down the tree may represent a word (or at least a prefix to a word).
- Useful for algorithms that do not require looking at entire key.
- Performance based on height of trie, which is equal to maximum length of key/word (m).


#### Types:
- **R-Way Trie**: Characters stored in each node with children up to the number of characters in the set.
- **Ternary Search Trie**: Characters stored in each node with 3 children. Smaller (left), equal (middle), larger (right). More space efficient than R-way trie.

#### Algorithms:
- **Prefix match** searches for all keys with a given prefix
- **Wildcard match** searches each branch in node when wildcard specified for a character
- **Longest prefix** searches for keys that match the longest prefix of a word

#### Efficiency:
- Search:     O(m)
- Insertion:  O(m)
- Deletion:   O(m)


### **Sources**

 - <http://bigocheatsheet.com>
 - <https://www.coursera.org/course/algs4partI>
 - <https://gist.github.com/TSiege/cbb0507082bb18ff7e4b#file-the-technical-interview-cheat-sheet-md>