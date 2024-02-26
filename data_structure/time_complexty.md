# o(n)
```c
#include <stdio.h>

int sum_array(int arr[], int size) {
    int total = 0;                 // O(1) - Constant time operation, independent of input size
    for (int i = 0; i < size; i++) { // O(n) - Linear time complexity, where n is the size of the input array
        total += arr[i];           // O(1) - Constant time operation, independent of input size
    }
    return total;                 // O(1) - Constant time operation, independent of input size
}

int main() {
    int array[] = {1, 2, 3, 4, 5};
    int size = sizeof(array) / sizeof(array[0]); // Calculate the size of the array
    int result = sum_array(array, size);
    printf("Sum of array elements: %d\n", result);
    return 0;
}
```

Now, let's break it down line by line:

1. `int sum_array(int arr[], int size) {`: This line defines a function named `sum_array` that takes an integer array `arr` and its size `size` as input. This operation takes constant time, denoted as O(1).

2. `int total = 0;`: This line initializes an integer variable `total` to store the sum of array elements. It's a constant time operation, O(1).

3. `for (int i = 0; i < size; i++) {`: This line starts a loop that iterates through each element in the input array `arr`. The loop runs 'n' times, where 'n' is the size of the array. Hence, its time complexity is O(n).

4. `total += arr[i];`: This line adds the current element `arr[i]` to the `total`. It's a constant time operation, O(1).

5. `return total;`: This line returns the final sum `total`. It's also a constant time operation, O(1).

Overall, the time complexity of the `sum_array` function is the sum of the time complexities of each line:

O(1) + O(n) + O(1) + O(1) = O(n)

So, the overall time complexity of the `sum_array` function is O(n), where 'n' is the size of the input array.



## To demonstrate a function with a time complexity of O(n^2) in C programming, let's consider an example where we have nested loops iterating over the elements of an array:

```c
#include <stdio.h>

void print_pairs(int arr[], int size) {
    for (int i = 0; i < size; i++) {      // O(n)
        for (int j = 0; j < size; j++) {  // O(n)
            printf("(%d, %d)\n", arr[i], arr[j]);
        }
    }
}

int main() {
    int array[] = {1, 2, 3, 4};
    int size = sizeof(array) / sizeof(array[0]);
    print_pairs(array, size);
    return 0;
}
```

Now, let's analyze the time complexity line by line:

1. `void print_pairs(int arr[], int size) {`: This line defines a function named `print_pairs` that takes an integer array `arr` and its size `size` as input. This operation takes constant time, denoted as O(1).

2. `for (int i = 0; i < size; i++) {`: This line starts the outer loop that iterates through each element in the input array `arr`. The loop runs 'n' times, where 'n' is the size of the array. Hence, its time complexity is O(n).

3. `for (int j = 0; j < size; j++) {`: This line starts the inner loop within the outer loop, iterating through each element in the array again. Since this loop is nested within the outer loop, it runs 'n' times for each iteration of the outer loop, resulting in a time complexity of O(n) * O(n) = O(n^2).

4. `printf("(%d, %d)\n", arr[i], arr[j]);`: This line prints the pairs of elements from the array. It's a constant time operation, denoted as O(1).

Overall, the time complexity of the `print_pairs` function is the product of the time complexities of each loop:

O(n) * O(n) = O(n^2)

So, the overall time complexity of the `print_pairs` function is O(n^2), where 'n' is the size of the input array.
