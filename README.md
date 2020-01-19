# Post-Bootcamp Topics

Created By: Chris Trinh
Last Edited: Jan 17, 2020

Markdown files were exported with Notion. It doens't seem to have the dropdown so I'll update the main read me soom

# Post-Code Bootcamp School

After graduating from a coding bootcamp in December 2019, I realized that this there is so much more to learn in the world of software and everything I learned the past months prior is just the very basics of information needed to actually have a successful career.

## Study Tips

I tried all sorts of study techniques through my undergraduate days and as I was going through bootcamp to learn to code. After scouring the internet one day for study tips and tricks, I came across two very important techniques to learning a skill that I feel are valuable to not just programmers but anyone. 

- [Active Recall](https://en.wikipedia.org/wiki/Active_recall) - This is the notion of efficient learning proven by studies that says all we need to learn is to stimulate memory during out learning process. I always wondered how people got into medical school with the vast amount of knowledge that they need to learn and this is one of the tricks they use to achieve that goal. One of my favorite youtubers is a Cambridge University medical student has a [video](https://www.youtube.com/watch?v=ukLnPbIffxE&t=1072s) on active recall and I recommend you guys check him out!
- The other technique is [Space Repetition](https://en.wikipedia.org/wiki/Spaced_repetition) which uses a space time period between learning concepts in order to increase the learning and memorization. I use this a lot with conceptual information like remembering which data structures does what, their time/space complexities, etc.

## Technologies

This section will be  the technologies that I will be planning to use and learn as I'm studying mostly data structures and algos for the next couple of months. I believe some interviews will ask you to build something (not sure for juniors) so being able to build simple CRUD applications and practicing daily is crucial for success.

<details>
<summary>Javascript</summary>
    
* [Map vs Object](https://medium.com/front-end-weekly/es6-map-vs-object-what-and-when-b80621932373)
* Hoisting & Anonymous Functions
* Closures

</details>

<details>
<summary>React</summary>
    
* React Hooks

</details>

<details>
<summary>Ruby</summary>

</details>

<details><summary>Python</summary></details>
<details><summary>GraphQL</summary></details>

## Topics

I made an outline of things I need to go over while and during the interview applying process, this is just a outline and as I go through each topic, I will be updating with helpful links/resources that will help.

<details>
<summary>Data Structures</summary> 

* ## Arrays
  * Arrays are stored contiguous in memory
  * Static array has a fixed length at compile time
  * Dynamic arrays grows as the elements in the array increases
  * Amortized Analysis is the complexity of an algorithm
  * Accessing an element takes O(1) time
  * Traversing an array takes O(N) time
  * Copying an array takes O(N) time and space
  * Inserting into an array takes O(N) time because we have to shift elements N spaces
  * .pop() is O(1) since we are removing from the end and not shifting
    * .shift() is O(1) we have to move elements accordingly
* ## Strings
  * Strings are stored as an array of integers in ASCII encoding standards in memory
  * Traversing a string takes O(N) time
  * Copying a string takes O(N) time and O(1) space
  * Retrieving an element in a string is O(1) time because in memory, they are stored as an array of integers
  * Strings are immutable for most modern languages
* ## Linked List
  * Sequence of nodes that are stored non-contiguously in memory
  * Properties of a head, tail, and length
  * Singly, doubly, multiply, and circularly linked
  * Access and Search take O(n) time and space
  * Insert and Delete take O(1) time and O(n) space
* ## Stacks && Queues
  * Stacks = LIFO (stack of books)
  * Queue = FIFO (line to pay groceries)
  * Both have O(1) add/delete time complexity 
  * Searching elements takes O(N) time
  * Storing elements takes O(N) time
* ## Hash
* ## Trees
  * Balanced vs Unbalanced Tree
    * 
  * Heap / Priority Queue / Binary Heap
  * Tries
* ## Graphs
  * How to do graph problems?
    * Use a structure to check visited nodes while traversing
    * DFS or BFS
  * Vertices are nodes and edges are the connections
  * Directed vs Undirected Graph
  * Cyclic Graph
  * Traversing a graph takes O(V + E) time and Space is O(V + E) where V is the number of nodes and E is the number of edges connecting each node
</details>

</details>

<details>
<summary>Trees</summary>
    
  * Breadth-first Search (DFS) 
  * Depth-first Search (DFS)
  * In-Order
    * left, self, right
  * Pre-Order
    * self, left, right
  * Post-Order 
    * left, right, self
  * Binary Search Trees (BST)
    * Properties
      * Nodes have at most 2 children
      * All values on the left of a node are less than its value
      * All the values on the right must be greater than the value
    * Insert, Delete, Search are all O(log n) time
    * Height is the number of edges between root and farthest leaf in the tree
  + Heap / Priority Queue / Binary Heap

</details>
<details>
<summary>Memory</summary>

* Memory lives in a bounded canvas in the computer that can store data.
* Memory is stored as base2 format or BITS
* Back to Back memory spots are slots that are right next to each other
* Bits is the unit used in memory (0s and 1s)
* One memory slot holds 8 bits or 1 byte
* Endianness is the order of bytes representing information in binary form

</details>
<details>
<summary>Binary Search</summary>

* Is the array sorted?
* O(log n) time
</details>

<details>
<summary>Bitwise Operations</summary>

</details>

<details>
<summary>Sorting</summary>

* General Information
* Stability
* Time / Space Complexity
* Merge Sort
* Quick Sort
* Radix Sort
* Bubble Sort
* Insertion Sort
* Selection Sort
</details>


<details>
<summary>System Design</summary>
</details>

<details>
<summary>Extra</summary>
    
* Recursion
* Dynamic Programming
* Object-Oriented Programming
* Design Patterns
* Cache
* Processes and Threads

</details>

<details>
<summary>CSS</summary>
</details>

# Resources

- [AlgoExpert](https://www.algoexpert.io/product) (code: gcmrn-32 15% off!)
- [LeetCode](https://leetcode.com/) (Buy Premium!)
- [75 LeetCode Questions to Save Your Time](https://www.teamblind.com/post/New-Year-Gift---Curated-List-of-Top-100-LeetCode-Questions-to-Save-Your-Time-OaM1orEU)
- [Grokking the System Design Interview](https://www.educative.io/courses/grokking-the-system-design-interview)
- [System Design Repo](https://github.com/donnemartin/system-design-primer)
- [Mock Interview Practice](https://www.pramp.com)
- [Design Patterns](https://hackernoon.com/14-patterns-to-ace-any-coding-interview-question-c5bb3357f6ed)
- [30 Vanilla Javascript Frontend Projects](https://javascript30.com/)


# Other

This list is not comprehensive but feel free to reach out on ideas to make studying more efficient! Also, I'm not 100% sure of the technical interview process so if any topics I laid out are wrong or not correct, don't hesitate to reach out!
