# Heaps

Created By: Chris Trinh
Last Edited: Jan 02, 2020 3:14 PM

- What is a heap?
    - A type of binary tree but **not** a binary search tree.
- Whats the difference between a binary search tree and a binary heap?
    - Heaps are partially ordered while binary search trees are fully ordered
- What are the properties of a heap?
    - Given any node, all children must be less than or equal to the node
    - There is no guaranteed order between siblings of a node
- What is a max heap?
    - A node will be greater than all its children, grandchildren, etc.
- What is a min heap?
    - Opposite of a max heap, a node is less than all of its children, grandchildren, etc..
- What does it mean to be a complete tree?
    - Tree where all levels have maximum number of nodes except the bottom level
    - Bottom level nodes have it filled to the far left as possible
    - Packing its node as closely as possible
- What does it mean to be a balanced tree?
- When do you use heaps?
    - When problems deal with 'partially sort' data
    - e.g calculating the smallest/largest n numbers in a collection
        - finding the largest 5 numbers in an array using linear time. Cant use sorting algos because O(n log n). heaps are O(n0
- What data structure will be used in constructing a heap?
    - Arrays, each index will represent a node and the root being at index 1
    - index 0 will always be null
- Describe the relationship from child to parent node
    - If we are given a node at index i, then the parent is found at Math.floor(i / 2)

- Whats 'siftup' for insertion?
    - When inserting a node, we insert to the bottom level of the heap and placed at the far left.
    - Placing a node there momentarily breaks the heap propery to we need to move the node up the tree and swap the node with its parent.

- Describe the delete max of heaps.
    - Root of heap will always be at max value, we want to delete and return the root while keeping the property
    - We save reference of the root value to return later, locate the right most node at the bottom and the copy the value to the root. then delete the duplicate to maintain heap property.
- What is 'siftdown' for deletion?
    - When we are deleting a node, we move the bottom to the root and now we break the nodes children must all be less than.
    - We will continue to swap the node down until its in a legal position.
- What is a time complexity of heaps?
    - Inserting and deleting the max is both O(log(n)) because we have to sift up or sift down the whole tree at half the level.
- What is the space complexity?
    - Since we are creating a single array to store data, then O(n)
- What is amortized mean?
    - meaning the analysis is about performance over many insertions
    - So its actually O(n) to heapify