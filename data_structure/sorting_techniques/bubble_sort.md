# bubble sort

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

## Bubble Sort Coding

`0-bubble_sort.c`

```jsx
#include <stdio.h>
#include "sort.h"
/**
 * bubble_sort - sort array lements from min to max value
 * @array: array
 * @size: array size
 */
void bubble_sort(int *array, int size)
{
		int i, j;
		int tmp;
	if (size < 2)
	return;
	for (i = 0; i < size - 1; i++)
	for (j = 0; j < size - 1 - i; j++)
{
if (array[j] > array[j + 1])
{
		tmp = array[j];
		array[j] = array[j + 1];
		array[j + 1] = tmp;
		print_array(array, size);
}
}
}
```

`sort.h` 

```jsx
#ifndef SORT_H
#define SORT_H
#include <stdlib.h>

/**
 * struct listint_s - Doubly linked list node
 *
 * @n: Integer stored in the node
 * @prev: Pointer to the previous element of the list
 * @next: Pointer to the next element of the list
 */
typedef struct listint_s
{
const int n;
struct listint_s *prev;
struct listint_s *next;
} listint_t;
void bubble_sort(int *array, int size);
void print_array(const int *array, size_t size);
void print_list(const listint_t *list);
void insertion_sort_list(listint_t **list);
void selection_sort(int *array, size_t size);
void quick_sort(int *array, size_t size);
void quick_sort_hoare(int *array, size_t size);
#endif
```

a line-by-line explanation of the code:

```c
#include <stdio.h>
#include "sort.h"

```

- This section includes necessary header files. `#include <stdio.h>` is a standard library for input and output operations, while `"sort.h"` likely contains function declarations related to sorting, although its contents are not shown here.

```c
/**
 * bubble_sort - sorts array elements from min to max value
 * @array: array to be sorted
 * @size: size of the array
 */

```

- This is a documentation comment for the `bubble_sort` function. It describes the purpose of the function and its parameters. `@array` represents the array to be sorted, and `@size` represents the size of the array.

```c
void bubble_sort(int *array, int size) {

```

- This line defines the `bubble_sort` function. It takes an array of integers (`int *array`) and its size (`int size`) as parameters.

```c
    int i, j;
    int tmp;

```

- Here, two integer variables `i` and `j` are declared for loop counters, and `tmp` is declared to temporarily store values during swapping.

```c
    // Check if the array has less than 2 elements, if so, return
    if (size < 2)
        return;

```

- This `if` statement checks if the array size is less than 2. If the array contains only one element or no elements, there is no need to sort it, so the function returns early.

```c
    // Outer loop controls the number of passes through the array
    for (i = 0; i < size - 1; i++) {

```

- This line begins an outer loop that controls the number of passes through the array. It iterates `size - 1` times because after each pass, the largest element will be correctly positioned at the end of the array.

```c
        // Inner loop performs comparison and swapping operations
        for (j = 0; j < size - 1 - i; j++) {

```

- This line starts an inner loop that performs comparison and swapping operations within each pass. It iterates from the beginning of the array up to `size - 1 - i` to avoid unnecessary comparisons with already sorted elements at the end of the array.

```c
            // If current element is greater than the next element, swap them
            if (array[j] > array[j + 1]) {
                tmp = array[j];
                array[j] = array[j + 1];
                array[j + 1] = tmp;

                // Print the array after the swap
                print_array(array, size);
            }
        }
    }

```

- Within the inner loop, this block of code checks if the current element is greater than the next element. If so, it swaps them. After each swap, the `print_array` function is called to print the array's current state.

This code implements the Bubble Sort algorithm, which sorts an array of integers from smallest to largest.
