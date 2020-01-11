# Stacks and Queues

Created By: Chris Trinh
Last Edited: Jan 03, 2020 10:06 PM

- What is a Stack?
    - Stack of books, LIFO
- What is a Queue?
    - A line, FIFO
- What is the insert/delete time complexity of both data structures?
    - O(1) time and space complexity;
- How does it work?
    - A stack is a dynamic array under the hood so adding/popping elements at the end is amortized operations
    - Searching element in the stack happens in a linear time and you cannot add to the bottom or the middle of the stack
    - A queue is implemented with a linked list so you can add or remove the first and last element with constant time.
- What is the complexity of searching?
    - O(n) time and constant space;
- What is the complexity of storing elements?
    - O(n) space to store
- What is a min and max stack?
    - A stack that keeps track of min and max elements
- What is a priority queue?
    - Keeps track of elements with high priority