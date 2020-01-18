# Linked List

Created By: Chris Trinh
Last Edited: Dec 23, 2019 11:20 AM

- What is a linked list?

    Linear sequence of nodes

- What are some linked list properties?

    Head - first node in the list

    Tail - last node in the list

    Length - number of nodes in the list

- What is a node?
- What are the some node properties?

    Value - value that the node represents

    Next - the next node in the list relative to the current node

    Previous - the previous node in the list

- How are arrays and linked lists different?

    Arrays contain contiguous data. Each element of an array is actually stored next to it's neighboring element in the actual hardware of your machine, in a single continuous block in memory.

    Linked Lists contain non-contiguous data. Though Linked Lists represent data that is ordered linearly, that mental model is just that - an interpretation of the representation of information, not reality.

- Why do linked list nodes have no indices and thus no random access?

    Nodes are not stored in a single continuous block of addresses. Rather, Linked List Nodes live at randomly distributed addresses throughout your machine! The only reason we know which node comes next in the list is because we've assigned its reference to the current node's next pointer.

- What is singly linked?

    Nodes have a single pointer connecting them in a single direction.Nodes have two pointers connecting them bi-directionally.

- What is doubly linked?

    Nodes have two pointers connecting them bi-directionally.

- What is multiply linked?

    Nodes have two or more pointers, providing a variety of potential node orderings.

- What is Circularly linked?

    Final node's next pointer points to the first node, creating a non-linear, circular version of a Linked List.

What is the linked list time complexity of:

- Access

    Time Complexity: O(n)

    Space Complexity: O(n)

- Search

    Time Complexity: O(n)

    Space Complexity: O(n)

- Insertion

    Time Complexity: O(1)

    Space Complexity: O(n)

- Deletion

    Time Complexity: O(1)

    Space Complexity: O(n)

What is the space complexity of a linked list; 

- We're given a Linked List, and need to operate on it.

    In Scenario 1, we are not creating a new Linked List. We simply need to operate on the one given. Since we are not storing a new node for every node represented in the Linked List we are provided, our solution is not necessarily linear in space.

- We've decided to create a new Linked List as part of strategy to solve some problem.

    In Scenario 2, we are creating a new Linked List. If the number of nodes we create is linearly correlated to the size of our input data, we are now operating in Linear Space.