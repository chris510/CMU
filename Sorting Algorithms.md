# Sorting Algorithms

Created By: Chris Trinh
Last Edited: Dec 22, 2019 2:53 PM

**Merge Sort**

- What is the general overview of merge sort?
    1. Split the arrays into a single assorted array then merge them together.
- What does the main mergesort function do?
    1. Split in half at the middle index and then recursively slice.
- What does the merge helper function do?
    1. Smallest number is at the front of the array, compares both first elements of the input arrays then add the smaller element from in the input into the new until both inputs are empty
- What is 0 in javascript?

    Falsey value that acts like 'false' all other numbers are truthy

- What does ‘Infinity’ do in javascript?

    A value that is greater than any other number

- What is the time complexity run time of the merge sort algorithm? Why?
    - `n` is the length of the input array
    - We must calculate how many recursive calls we make. The number of recursive calls is the number of times we must split the array to reach the base case. Since we split in half each time, the number of recursive calls is `O(log(n))`.
        - for example, say we had an array of length `32`
        - then the length would change as `32 -> 16 -> 8 -> 4 -> 2 -> 1`, we have to split 5 times before reaching the base case, `log(32) = 5`
        - in our algorithm, **log(n)** describes how many times we must halve **n** until the quantity reaches 1.
    - Besides the recursive calls, we must consider the while loop within the `merge` function, which contributes `O(n)` in isolation
    - We call `merge` in every recursive `mergeSort` call, so the total complexity is **O(n * log(n))**
- What is space complexity of merge sort?

    The larger the size of our input array, the greater the number of subarrays we must create in memory. These are not free! They each take up finite space, and we will need a new subarray for each element in the original input. Therefore, Merge Sort has a linear space complexity, O(n).

- Why should we use merge sort?

    If you have unlimited memory

**Quick Sort**

- What is the general overview of quick sort?

    Divide the input array into two subarrays; one with the smaller elements, and one with the larger elements. Then, it recursively operates on the two new subarrays, and continues this process until we reach subarrays of length 1 or smaller

- What is the time complexity of ‘forEach, ‘filter’, and 'partition' function?

    O(n), time complexity. Although our fancy partition does filter twice, this is a constant we drop, O(2n) = O(n). Linear time is fast so we are quite happy with partition.

- What does the spread operator do and how can you use that to concatenate arrays?
- What is the time complexity of quick sort?
    - `n` is the length of the input array
    - The parititon step alone is `O(n)`
    - We must calculate how many recursive calls we make. The number of recursive calls is the number of times we must split the array to reach the base case. This is dependent on how we choose the pivot. Let's analyze the best and worst case:
        - **Best Case:** We are lucky and always choose the median as the pivot. This means the left and right partitions will have equal length. This will halve the array length at every step of the recursion. We benefit from this halving with `O(log(n))` recursive calls to reach the base case.
        - **Worst Case:** We are unlucky and always choose the min or max as the pivot. This means one partition will contain everything, and the other partition is empty. This will decrease the array length by 1 at every step of the recursion. We suffer from `O(n)` recursive calls to reach the base case.
    - The parition step occurs in every recursive call, so our total complexities are:
        - **Best Case:** O(n * log(n))
        - **Worst Case:** O(n ^ 2)
- How does the choice of pivot affect the efficiency of the algorithm?

    Although we typically take the worst case when describing Big-O for an algorithm, much research on quickSort has shown the worst case to be an exceedingly rare occurance even if we choose the pivot at random. Because of this we still consider quickSort an efficient algorithm. This is a common interview talking point, so you should be familiar with the relationship between the choice of pivot and efficiency of the algorithm.

- If the median is the best pivot, why can’t we always choose the median element?

    To know the median of an array, the array needs to be sorted.

- What is the space complexity of quick sort?

    O(n) space because of the partition arrays we create. There is an in-place version of quickSort that uses O(log(n)) space. O(log(n)) space is not huge benefit over O(n). You'll also find our version of quickSort as easier to remember, easier to implement. Just know that a O(logn) space quickSort exists.

- When would quick sort be used? Over merge sort?
    - When you are in a pinch and need to throw down an efficent sort (on average).
    - When constant space is important to you, use the in-place version. This will of course trade off some simplicity of implementation.
    - If you know your input data to be mostly already sorted, randomize the choice of pivot

**Radix Sort**

- What is radix sort and what is it used for?
    - Non-comparison integer sorting algorithm. Can only be used for sorting integer data and on lists of binary numbers
- How can we determine the relative size of an integer?
    - Based on the number of digits it has
- How does radix sort work?
    1. Use buckets from 0-9
    2. Move integers based on first integer, the second integer, then so on.
- What does the first helper function, getDigitFrom do?
    - Absolute value to avoid getting back negative digits.
    - Divide by Math.pow(10, i) to divide integer by it's place value, 10.

        place

    - Floor to round away any decimals.
    - Mod 10 to get the digit of interest.
- What does the second helper function getIntlength do?
    - We need to know the number of digits of the largest number in our list.This is how we know how many times to run through or algorithmic process; how many times to bucket and unbucket our numbers.
- What does the third helper function getMaxDigits do?
    - Gives us the max digit length of the entire input
- What is the time complexity of radix sort?
    - requires iterating over all n elements of the input array, and doing so k times, where k is the length (number of digits) of the longest integer in the array, we wind up with a run time of O(n * k).
- In computer science debate, what does the input array do to the time complexity if it is filled with entirely unique values?
    - due to a characteristic of the way computers store numerical data, that k becomes log k
- What is the absolute worst case complexity scenario and why?
    - length of the longest integer in the input array, k, is equal to (or greater than) the total number of elements in the array, n. In this scenario, we wind up with an O(n log(k)), or approximately O(n log(n))
- What is the space complexity of radix sort?
    - The amount of memory consumed by the algorithm increases relative to both the size of the input array and the length of the longest integer.
    - O(n + k) space
- When should we use radix sort?
    - Sort a list of any sort of binary data, including numeric, text, or image data in binary format.
    - Sort a list of integers, and you *don't* know the value of the largest element in the list.

**Counting Sort**

- What is counting sort and what is it used for?

    Sort integer data

- What are the steps in counting sort implementation?
    1. Find starting index for each number
    2. Adding each number to the accumulation to the right.
    3. Shift numbers to the right, this is the starting position.
- What must we know before implementing this algorithm? Why do we need to know this in advance?

    The largest input value of the array, we need to know how long the counter array is so when we itterate and find an uncounted integer, we have a position to count it.

- Why will arrays be used in this algorithm?

    Arrays contain indices for each index position so it will be easier to 'count'

- What does javascript ‘fill’ method do?

    Given array input, fill each value at each index with argument given

- What is the time complexity for counting sort?
    - Iterating over all n elements of the input array, and then subsequently iterating over our each element of our counter array (which has length k), we wind up with a run time of O(n + k). This makes Counting Sort faster than any of the previous comparison-based algorithms, and also faster than Radix Sort!
- What is the space complexity for counting sort?
    - The smaller the range of integers that can possibly occur in our input array, the more memory efficient Counting Sort will be. The larger k is, the larger the number of elements we'll have to allocate in our counter array. Thus, the space complexity of Counting Sort is O(k).
    - In an interview setting, always ask the interviewer if you can be guaranteed that the largest element in the input array is not huge.
    - If asked why, mention that you may choose to use the Counting Sort algorithm to achieve a linear sort, but are considering the memory-cost trade offs involved. According to the ECMA-262 5th edition spec, due to 32-bit numbers, the upper-bound length of a JavaScript array is 2^32 - 1, which is 4,294,967,295. If the largest possible integer in your array is larger than this, you'll have to optimize the Counting Sort algorithm to use less total memory if you intend to use it.
- What are the trade offs between time and space complexity and how can we consider this?

    The smaller the range of integers that can possibly occur in our input array, the more memory efficient Counting Sort will be

- When do we use counting sort?
    - Sort a list of integer data, and you *do* know the value of the largest element in the list.
        - If you *do not* know the largest element in the list, see `radixSort`!
    - Counting Sort's run time, O(n + k), is dependent on the size of the largest integer in the input, `k`. For this reason, it is fastest when `k` is relatively small.