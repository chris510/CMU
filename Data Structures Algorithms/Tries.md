# Tries

Created By: Chris Trinh
Last Edited: Jan 11, 2020 6:48 PM

- What are Tries?
    - Type of search tree used to efficiently store a set of strings for later retrieval
- Why are tires known as prefix trees?
    - path from root to any note will represent a prefix with atleas one string in a set.
- How many children can Tries have?
    - Since tries are not binary trees, they can have any number of children
- What is usually stored in tries?
    - We don't store values within the nodes of a trie but the edges could be used as reference to the letters of an alphabet
    - Recognized words must begin at the root and then end at a "terminal node" or root

- How does the trie insert work?
    - If we want to insert a character into the trie, we have to check to see if it already exists or not, then we want to do a check if we want to use it or check the edge for it?
- How does search work?
    - Traverse the tree until we reach the terminal node.
    - We search by the first letter of the word each time and then if we find it we will move on. If the edge doesn't exist when we reach the terminal node then we know it is not in a tree
- What is the complexity?
    - insert and search requires O(m) time where m is the length of a target word because we are only traversing the trie to find the given word length
    - O(n *m) space complexity because it depends if prefixes and shared between words or entries. where n is the number of words and m is the maximum length of any word.
- When should we use tries?
    - We need to store a dictionary of words and need efficient look up to check if a word is in the dictionary.
    - Trie is guranteed to be worst case O(m) where m is the length of the desired word where has structures are O(n) where n is the the number of entries in the dictionary hash.