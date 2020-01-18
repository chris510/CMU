# AlgoExpert Conceptuals

Created By: Chris Trinh
Last Edited: Jan 10, 2020 7:27 PM

**Memory**

- What is Memory?
    - Bounded canvas of memory slots that live somewhere in the computer that can store data.
    - Bounded = limited amount of data to be stored and run out of memory; why space complexity is important
- What is the format memory is stored?
    - Base 2 format as bits
- How does a program store memory slots?
- What are back to back memory spots?
    - Memory slots that are right next to each other
- What is the unit used for memory?
    - Bits (Zeros and One's)
- What does one memory slot hold?
    - 8 Bits or 1 byte
- How do we store information into slots if memory are zero and ones
    - We can convert information into binary numbers
- What is a binary number?
- What is positional notation?
- What is endianness?

    Order of bytes when representing information in binary

- What is the access complexity of a memory slot?
    - inexpensive basic operation that is very fast!

**Arrays**

- What is a static array?
    - allocated memory at compile time and the memory is allocated on the stack
- What is a dynamic array?
    - allocated memory at the runtime and the memory is allocated from heap
    - array under the hood that gives you faster insertions because it allocates twice as much memory based on initial length of the array.
    - Once you go up to the limit of that place, you have constant insertion until you copy and then create another double the amount of space that you need
    - O(1) Time complexity
        - Every time we double the memory its O(N)
        - Inserting into the array max length is O(1)
    - O(1) Space complexity
- What is amortized Analysis?
    - Discussing complexity when taking into account all the edge cases
- What does it mean for access to an element in the array is instant? (get)
    - Accessing any element is constant because every element in the array is fixed-width (never changing) because the index of each element in the array is known because we now the max width
    - O(1) space and time
- What is the complexity of set in an array?
    - Accessing the memory slot is instant time since we find the element and overwrite the same memory with different binary numbers
    - O(1) space and time
- What is the initialize complexity?
    - O(n) space and time because we have to add operations with respect with the input size. 8 bits * n size
- What is the traversing complexity of an array?
    - O(n) time since we have to go through all the memory spots
    - O(1) space
- What is the copying complexity of the array?
    - Traversing through the array: O(N) time and O(N) space because we are making the same array in memory blocks
- What is the complexity of inserting a value into an array at any spot?
    - We have to shift all the blocks and add another spot in memory if needed.
    - Sometimes, if there is no back to back memory spots, we have to move to another spot in memory.
        - Have to copy and then add the element
    - O(N) time and O(1) Space
- What is .shift time complexity in javascript and why?
    - O(N) because we have to insert in the beginning and then move all the other elements over
- What is .pop time complexity in javascript?
    - At the end, its O(1)
    - At the beginning or middle, its O(N) because we have to shift the elements

**Strings**

- How are strings stored in memory?
    - As an array of integers through character encoding standards like ASCII (256)
        - A = 65, B = 66, a = 97
    - Using a fixed amount of bytes
- What is the complexity of the operations done on a string?
    - constant O(n)
- What is the complexity of traversing?
    - O(n) time
    - O(1) space
- What is the complexity of copying?
    - O(n) time, since we have to itterate through
    - O(n) space
- What is the complexity of get?
    - O(1) space and time because the string is stored as an array of integers
- What is the complexity of mutating a string?
    - strings are immutable for most modern languages(not C++);
    - In order to change the string at a certain spot, we need to copy and then alter that point
    - O(n) time and space operation because of the above.

**Linked List**

- How are linked list stored in memory
    - Unlike arrays where the elements are stored contiguously, linked list could be stored in different memory slots and are able to relate to each other through pointers
    - Linked list are not stored back to back and can be stored anywhere in memory
- What is the complexity getting an element in a linked list?
    - O(i) time complexity where i is the index;
    - O(1) space complexity
- What is the complexity of traversing a element in a linked list?
    - O(n) time and space because we have to move through the whole size of the linked list
- What is the complexity of copying a linkedlist?
    - O(n) time complexity and O(1) space
- What is the complexity of setting an element in a linked list?

    O(i) time because we have to find the i

    O(1) space complexity

- What is the complexity of initializing a linked list?
    - O(n) space and time complexity because theres a value and pointer for each memory slot. (e.g 2 memory slots per node)
    - Allocating chunks of memory takes O(n) time
- What is the complexity of inserting and deleting an element into a linked list?
    - O(1) constant time
    - If inserting a linked list in a position, we have to traverse the list until we reach the position
    - Creating a new node with x memory slots and then shifted the pointers
    - With an array we need to shift the element every time we add to the element

**Trees**

- What are min and max heaps?
    - binary search trees where the tree satisfy the min and max heap properties
- What are the min heaps properties?
- What are the max heaps properties?
- What is the space complexity of a tree?
    - O(n) where n is the number of nodes
- What is the traversing complexity of tree?
    - O(n) if you want to traverse through all the nodes
    - If you are only traversing half a tree (one path), then its O(log n)
- What is a balanced binary tree and complexity?
    - Likely O(n) and where each node traverse gets cut in half
    1. The left and right subtrees' heights differ by at most one, AND
    2. The left subtree is balanced, AND
    3. The right subtree is balanced
- What are some advanced type of trees and how are they so good?
    - e.g Red black trees that automatically rebalance themselves so that they can keep their O(log n) time complexity

**Graphs**

- What is a graph?
    - Collection of nodes that may or may not be connected to each other
- What is are vertices and edges
    - Vertices are nodes and edges are the connections
- What are the key concepts when looking at a graph?
    - Whether a graph is connected or not. Graphs can contain nodes that will not be able to reach other
- What is a directed graph vs undirected graph
    - One node connecting to another node or a node has a interconection
    - e.g airplane flights vs friendship connection
- What is a cyclic graph?
    - A graph that has a cycle of nodes, otherwise its acyclic
    - e.g Wikipedia linking system
- How to do graph problems?
    - Marking nodes as visited when traversing because it could end up in an infinite loop (pattern)
    - Can store value in a hash table, can store edges as edges
    - dfs(deep) or bfs(wide)
- What is the time and space complexity?
    - Traversing takes O(V + E)
    - Space is O(V + E) where v is the number of nodes and values and e is the number of edges connecting