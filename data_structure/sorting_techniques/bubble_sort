# bubble sort

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/259ab5a1-7184-44a1-892d-71e027ec75e8/6ea084b5-5cf4-4529-8f62-7990fadb9930/Untitled.png)

## pseudo-code

```c
/**
 * for i from i to N
 *  for j from 0 to N - i
 *      if a[j] > a[j+1]
 *          swap(a[j],a[j+1])
*/
```

## Bubble Sort algorithm

The provided pseudo-code represents a variation of the Bubble Sort algorithm. Let's break it down:

```
/**
 * for i from i to N
 *  for j from 0 to N - i
 *      if a[j] > a[j+1]
 *          swap(a[j],a[j+1])
*/

```

This pseudo-code also describes the Bubble Sort algorithm, but with a slight optimization. Here's how it works:

1. **Outer Loop (for i from 0 to N):**
    - This loop iterates over each element in the array from index 0 to N (exclusive). It represents each pass of the bubble sort algorithm.
2. **Inner Loop (for j from 0 to N - i):**
    - This loop iterates over each element in the array from index 0 to N - i (exclusive). The optimization here is that with each pass of the outer loop, the largest element in the unsorted portion of the array (elements beyond index N - i) is already sorted. Therefore, there's no need to iterate over those elements again.
3. **Comparison and Swap:**
    - Inside the inner loop, it compares the element at index j with the element at index j+1.
    - If the element at index j is greater than the element at index j+1, it swaps them. This step ensures that after each iteration of the inner loop, the largest unsorted element "bubbles up" to its correct position at the end of the current unsorted portion of the array.

This optimization reduces the number of comparisons and swaps, improving the overall efficiency of the Bubble Sort algorithm.

Example:
Consider an array `a` with N elements:

```
a = [5, 3, 8, 2, 1]

```

**First Pass (i=0):**

- Inner loop (j=0 to 4):
    - Compare 5 and 3. Swap them. Array becomes: `[3, 5, 8, 2, 1]`
    - Compare 5 and 8. No swap needed.
    - Compare 8 and 2. Swap them. Array becomes: `[3, 5, 2, 8, 1]`
    - Compare 8 and 1. Swap them. Array becomes: `[3, 5, 2, 1, 8]`

**Second Pass (i=1):**

- Inner loop (j=0 to 3):
    - Compare 3 and 5. No swap needed.
    - Compare 5 and 2. Swap them. Array becomes: `[3, 2, 5, 1, 8]`
    - Compare 5 and 1. Swap them. Array becomes: `[3, 2, 1, 5, 8]`

**Third Pass (i=2):**

- Inner loop (j=0 to 2):
    - Compare 3 and 2. Swap them. Array becomes: `[2, 3, 1, 5, 8]`
    - Compare 3 and 1. Swap them. Array becomes: `[2, 1, 3, 5, 8]`

**Fourth Pass (i=3):**

- Inner loop (j=0 to 1):
    - Compare 2 and 1. Swap them. Array becomes: `[1, 2, 3, 5, 8]`

Now, the array is sorted, and the algorithm terminates.
