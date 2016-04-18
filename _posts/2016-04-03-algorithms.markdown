---
layout: post
title:  "Interviews: Algorithms"
date:   2016-04-03 20:00:00 -0800
categories: interviews
tags: interview algorithms
comments: true
---

This series contains review materials for software engineer interview questions. This guide provides a high-level overview of basic algorithms including their implementations, applications and efficiency.

### **Depth-First Search**

#### Overview:
- Systematically search through a tree or graph, start at the root.
  - E is number of edges.
  - V is number of vertices.
- Analyzes paths by searching depth of the tree or graph first (nodes farthest away).
- Algorithm implemented using a stack (LIFO).
  - Unvisited vertices added to stack.
  - Visited vertices are marked to deal with cycles in graph (not required for a tree).
  - Retrace steps when no unvisited options.
  - Typically implemented using recursion.
- Optimal for searching graphs and tress that are deeper than they are wide.

#### Applications:
- Find all vertices connected to a given source vertex.
- Find a path between two vertices.

#### Efficiency:
- Search: O\(\|E\| + \|V\|\)


### **Breadth First Search**

#### Overview:
- Systematically search through a tree or graph, start at the root.
  - E is number of edges.
  - V is number of vertices.
- Analyzes paths by searching closest nodes first.
- Algorithm implemented using queue (FIFO).
  - Put unvisited vertices in the queue.
  - Repeat until queue is empty.
    - Remove vertex v from queue.
    - Add to queue all unmarked vertices adjacent to v and mark them as visited.
- Examines vertices in increasing distance from root.
- Optimal for searching graphs and trees that are wider than they are deep.

#### Applications:
- **Shortest path:** Find path from s to t that uses fewest number of edges.
  
#### Efficiency:
- Search: O\(\|E\| + \|V\|\)


### **Binary Search**

#### Overview:
- Search through an array to locate a specific element.
- Algorithm typically implemented recursively.
  - Compare element x to the midpoint of the sorted array.
  - If x less than the midpoint, then search the left half of the array.
  - If x greater than the midpoint, then search the right half of the array.
  - Repeat the process treating the halves as subarrays until finding x or subarray is size 0.

#### Applications:
- Find element in sorted array.

#### Efficiency:
- Search: O\(log N\)


### **Quick Sort**

#### Overview:
- Comparison based sorting algorithm.
- Algorithm typically implemented recursively.
  - Shuffle the array (to ensure average element selected).
  - Partition array so that for some element x (typically first element of subarray).
    - Entry a\[x\] is in place.
    - No larger entry to the left of x.
    - No smaller entry to the right of x.
  - Sort each subarray.
  - Requires special handling for duplicate keys, otherwise quadratic performance.
- Quicksort is generally faster than mergesort.
- In-place sorting algorithm (constant extra space).
- Not a stable sorting algorithm (long range exchanges of elements).

#### Applications:
- Sort an array of elements.
- Java primitive type sorting uses quick sort.

#### Efficiency:
- Best Case Sort: O(N log N)
- Average Case Sort: O(N log N)
- Worst Case Sort: O(N^2)


### **Merge Sort**

#### Overview:
- Comparison based sorting algorithm.
- Algorithm typically implemented recursively.
  - Divide array into two (recursively).
  - Sort each subarray.
  - Merge the two subarrays.
- Merging algorithm.
  - Create a temporary array that is the same size as the two halves.
  - Keep track of three indices: output, first half, and second half.
- Not an in-place sorting algorithm (linear extra space).
- Stable sorting algorithm (maintains relative order of equal keys).

#### Applications:
- Sort an array of elements.
- Java generic object type sorting uses merge sort.

#### Efficiency:
- Best Case Sort: O(N log N)
- Average Case Sort: O(N log N)
- Worst Case Sort: O(N log N)


### Sources

 - <http://bigocheatsheet.com>
 - <https://www.coursera.org/course/algs4partI>
 - <https://gist.github.com/TSiege/cbb0507082bb18ff7e4b#file-the-technical-interview-cheat-sheet-md>