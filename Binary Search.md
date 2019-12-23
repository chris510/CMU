# Binary Search

Created By: Chris Trinh
Last Edited: Dec 21, 2019 7:37 PM

- How does binary search work?

    Think of a dictionary. A dictionary contains alphabetically sorted words and their definitions. A dictionary is pretty much only useful if it is ordered in this way. Let's say you wanted to look up the definition of "stupendous." What steps might you take?

    - you open up the dictionary at the roughly middle page
        - you land in the "m" section
    - you know "s" comes somewhere after "m" in the book, so you disregard all pages before the "m" section. Instead, you flip to the roughly middle page between "m" and "z"
        - you land in the "u" section
    - you know "s" comes somewhere before "u", so you can disregard all pages after the "u" section. Instead, you flip to the roughly middle page between the previous "m" page and "u"
    - ...
- What is the requirement in order to use binary search?

    The array needs to be sorted

- What is the time complexity of searching any array?

    O(n)

- What is the time complexity of binary search?
    - `n` is the length of the input arrayWe have no loops, so we must only consider the number of recursive calls it takes to hit the base caseThe number of recursive calls is the number of times we must halve the array until it's length becomes 0. This number can be described by `log(n)`for example, say we had an array of 8 elements, `n = 8`the length would halve as `8 -> 4 -> 2 -> 1`
- What is the space complexity of binary search?

    O(n)

    Our implementation uses n space due to half arrays we create using slice. Note that JavaScript slice creates a new array, so it requires additional memory to be allocated.