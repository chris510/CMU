# Array

Created By: Chris Trinh
Last Edited: Dec 31, 2019 5:16 PM

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