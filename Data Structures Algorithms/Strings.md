# Strings

Created By: Chris Trinh
Last Edited: Jan 01, 2020 9:24 PM

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