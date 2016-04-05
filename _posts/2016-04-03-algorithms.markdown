---
layout: post
title:  "Interviews: Algorithms"
date:   2016-04-03 20:00:00 -0800
categories: interviews
tags: interview algorithms
comments: true
---

This series contains review materials for software engineer interview practice. This guide provides a high-level overview of basic algorithms including their implementations, applications and efficiency.

### **Depth-First Search**

#### Overview:
- Systematically search through a tree or graph, start at the root.
  - E is number of edges.
  - V is number of vertices.
- Analyzes paths by searching depth of the tree or graph first (nodes farthest away).
- Algorithm implemented using a stack (LIFO).
  - Unvisited vertices added to stack.
  - Visited verticies are marked to deal with cycles in graph (not required for a tree).
  - Retrace steps when no unvisited options.
  - Typically implemented using recursion.
- Optimal for searching graphs and tress that are deeper than they are wide.

#### Applications:
- Find all verticies connected to a given source vertex.
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



### Sources

 - <http://bigocheatsheet.com>
 - <https://www.coursera.org/course/algs4partI>
 - <https://gist.github.com/TSiege/cbb0507082bb18ff7e4b#file-the-technical-interview-cheat-sheet-md>