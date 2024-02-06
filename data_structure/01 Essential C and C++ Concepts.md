# 01 Essential C and C++ Concepts (Array & Pointers & Classes)

Tags: In progress

## Pointer Usage

### Some reasons to use pointers are

- Passing address to function `call by reference`.
- Return more than one value from one `function to another`.
- Pass array and strings more conveniently from one `function to another`.
- `Manipulate arrays` more easily by moving pointers to them(or to parts of them), instead of moving the arrays themselves.
- `Create complex data structures`, such as Linked lists and binary trees, where one data structure must contain a reference to another data structure.

## Arrays

### Structure

- In C, a struct (short for structure) is a composite data type that allows you to group multiple variables together under a single name. Each variable within a struct is called a member or field.
- Here's the basic syntax for defining a struct:

```c

struct struct_name {
    // Member variables
    data_type1 member1;
    data_type2 member2;
    // ...
};

```

After defining a struct, you can declare variables of that type and access its members using the dot **`.`** operator.

Here's an example:

```c

#include <stdio.h>// Define a struct called 'Person' to represent a person's information
struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    // Declare a variable 'person1' of type 'Person' and initialize its members
    struct Person person1 = {"John", 30, 6.1};

    // Access and print the members of 'person1'
    printf("Name: %s\n", person1.name);
    printf("Age: %d\n", person1.age);
    printf("Height: %.2f\n", person1.height);

    return 0;
}

```

In this example:

- We define a struct called **`Person`** with three members: **`name`**, **`age`**, and **`height`**.
- Inside the **`main`** function, we declare a variable **`person1`** of type **`Person`** and initialize its members with values.
- We then access and print the members of **`person1`** using the dot **`.`** operator.

Structs are commonly used in C for organizing related data into a single unit, which makes it easier to manage and manipulate complex data structures. They are particularly useful for representing entities in the real world, such as people, cars, employees, etc.

### Array of Structure

- An array of structures in C is simply an array where each element is a structure. This allows you to store multiple instances of a structure in a contiguous block of memory. You can then access and manipulate each element of the array just like you would with any other array.
- Here's an example:

```c
#include <stdio.h>

// Define a struct called 'Person' to represent a person's information
struct Person {
    char name[50];
    int age;
    float height;
};

int main() {
    // Declare an array of 'Person' structures
    struct Person people[3];

    // Initialize the array elements
    people[0] = (struct Person){"John", 30, 6.1};
    people[1] = (struct Person){"Alice", 25, 5.5};
    people[2] = (struct Person){"Bob", 40, 5.9};

    // Access and print the members of each person in the array
    for (int i = 0; i < 3; i++) {
        printf("Person %d:\\n", i + 1);
        printf("Name: %s\\n", people[i].name);
        printf("Age: %d\\n", people[i].age);
        printf("Height: %.2f\\n", people[i].height);
        printf("\\n");
    }

    return 0;
}

```

In this example:

- We define a struct called `Person` to represent a person's information.
- Inside the `main` function, we declare an array `people` of `Person` structures with a size of 3.
- We initialize each element of the `people` array with different `Person` structures.
- We then use a loop to iterate over each element of the array and print the members of each `Person` structure.

Arrays of structures are commonly used in C for representing collections of related data, such as lists of employees, students, or any other entities with multiple attributes. They provide a convenient way to organize and work with such data in memory.

### **Resources**

[C Structures (structs)](https://www.w3schools.com/c/c_structs.php)

## Pointers

- The `Pointer` stores the `Address` of the data
- `Malloc` then only allocates in a `heap`

### **Why Pointers**

- **Pointers are used in C and many other programming languages for various reasons:**
1. **Dynamic Memory Allocation**: Pointers allow dynamic memory allocation, where memory can be allocated or deallocated during program execution. This enables efficient memory management and usage.
2. **Passing by Reference**: Pointers allow passing arguments to functions by reference, rather than by value. This means that changes made to the arguments inside the function will reflect outside the function, which can be useful for functions that need to modify the original variables.
3. **Data Structures**: Pointers are essential for implementing complex data structures such as linked lists, trees, graphs, and dynamic arrays. These data structures often require nodes to point to other nodes or to dynamically allocated memory locations.
4. **Accessing Memory Directly**: Pointers provide direct access to memory locations, which can be useful for low-level programming tasks such as system programming, device drivers, and interfacing with hardware.
5. **Efficiency**: Pointers can be more efficient than passing large data structures by value because they only need to store the memory address rather than the entire data structure. This can lead to faster function calls and less memory usage.
6. **String Manipulation**: Strings in C are typically represented as arrays of characters terminated by a null character (**`'\0'`**). Pointers are commonly used to manipulate strings efficiently, by pointing to the first character of the string.
7. **Dynamic Data Structures**: Pointers are crucial for managing dynamic data structures like dynamic arrays and linked lists, where the size of the data structure can change during runtime.
8. **Memory Optimization**: Pointers can help optimize memory usage by allowing sharing of memory across different parts of the program and enabling the reuse of memory locations.

### **Declaration**

**In C, pointers are declared using the `*` symbol. The general syntax for declaring a pointer is:**

```c
data_type *pointer_name;
```

Here, **`data_type`** specifies the type of data that the pointer will point to, and **`pointer_name`** is the name of the pointer variable. For example:

```c
int *ptr;  // Declares a pointer to an integer
float *ptr_f;  // Declares a pointer to a float
char *ptr_c;  // Declares a pointer to a character
```

It's important to note that the **`*`** symbol is used for both declaration and dereferencing pointers. However, when used in a declaration, it indicates that the variable being declared is a pointer.

To initialize a pointer to point to a specific memory address or to another variable, you can assign the address using the address-of operator **`&`** or assign another pointer:

```c
int x = 10;
int *ptr = &x;  // Pointer ptr now points to the memory location of variable x

int *ptr2 = ptr;  // Pointer ptr2 now points to the same memory location as ptr
```

Additionally, pointers can be initialized to **`NULL`** or **`0`** to indicate that they don't currently point to any valid memory location:

```c
int *ptr = NULL;  // Pointer ptr is initialized to NULL
```

Remember, dereferencing a pointer (accessing the value it points to) is done using the **`*`** operator:

```c
int x = 10;
int *ptr = &x;  // Pointer ptr points to the memory location of variable x
printf("%d\n", *ptr);  // Dereferences ptr to access the value it points to (prints 10)
```

### **Initialization**

- **In C, pointers can be initialized in several ways:**
1. **Initializing to NULL**: You can initialize a pointer to **`NULL`** to indicate that it doesn't currently point to any valid memory location.
    
    ```c
    int *ptr = NULL;
    ```
    
2. **Initializing to a Memory Address**: You can initialize a pointer to point to a specific memory address using the address-of operator **`&`**.
    
    ```c
    int x = 10;
    int *ptr = &x;
    ```
    
3. **Initializing to Another Pointer**: You can initialize a pointer to point to the same memory location as another pointer.
    
    ```c
    int *ptr1;
    int *ptr2 = ptr1;
    ```
    
4. **Initializing Dynamically Allocated Memory**: Pointers are commonly initialized to point to dynamically allocated memory using functions like **`malloc`**, **`calloc`**, or **`realloc`**.
    
    ```c
    int *ptr = malloc(sizeof(int));
    ```
    
5. **Initializing to an Array**: Pointers can be initialized to point to the first element of an array.
    
    ```c
    int arr[] = {1, 2, 3, 4, 5};
    int *ptr = arr;
    ```
    
6. **Initializing with Cast**: Sometimes, you might need to cast a pointer to a specific type before initializing it.
    
    ```c
    void *ptr_void = NULL;
    int *ptr_int = (int *)ptr_void;
    ```
    

Remember, initializing a pointer does not allocate memory for the data it points to (except in the case of dynamically allocated memory). It only sets the memory address that the pointer will point to. It's crucial to ensure that pointers are properly initialized before being dereferenced to avoid undefined behavior.

### **Dereferencing**

Dereferencing a pointer in C means accessing the value that the pointer is pointing to. This is done using the unary operator **`*`** followed by the pointer variable. Dereferencing allows you to read or modify the value stored at the memory location pointed to by the pointer.

**Here's how you dereference a pointer:**

```c
int x = 10;
int *ptr = &x;  // Pointer ptr points to the memory location of variable x

// Dereferencing ptr to access the value it points to
int value = *ptr;  // value now holds the value of x, which is 10
```

**You can also modify the value pointed to by the pointer by dereferencing it and assigning a new value:**

```c
int x = 10;
int *ptr = &x;  // Pointer ptr points to the memory location of variable x

// Dereferencing ptr to modify the value it points to
*ptr = 20;  // Now x holds the value 20
```

Dereferencing is a fundamental operation when working with pointers in C. It allows you to interact with and manipulate data indirectly through pointers. However, it's important to ensure that the pointer is valid and points to a valid memory location before dereferencing it, as dereferencing a null pointer or an uninitialized pointer can lead to undefined behavior and program crashes.

### **Dynamic Allocation**

Dynamic memory allocation in C is a process of allocating memory at runtime rather than compile time. This allows you to allocate memory dynamically based on program requirements. The standard library functions **`malloc`**, **`calloc`**, **`realloc`**, and **`free`** are commonly used for dynamic memory allocation and deallocation.

Here's a brief overview of each function:

1. **malloc**: This function is used to allocate a block of memory of a specified size. It takes the number of bytes to allocate as an argument and returns a pointer to the beginning of the allocated memory block. The memory allocated by **`malloc`** is uninitialized, meaning it contains garbage values.
    
    ```c
    int *ptr = (int *)malloc(10 * sizeof(int));
    ```
    
2. **calloc**: Similar to **`malloc`**, **`calloc`** is used to allocate memory, but it also initializes the allocated memory block to zero. It takes two arguments: the number of elements to allocate and the size of each element in bytes.
    
    ```c
    int *ptr = (int *)calloc(10, sizeof(int));
    ```
    
3. **realloc**: This function is used to resize a previously allocated memory block. It takes two arguments: a pointer to the original memory block and the new size in bytes. If resizing is successful, it returns a pointer to the newly allocated memory block, which may or may not be the same as the original pointer.
    
    ```c
    ptr = (int *)realloc(ptr, 20 * sizeof(int));
    ```
    
4. **free**: This function is used to deallocate memory that was previously allocated dynamically using **`malloc`**, **`calloc`**, or **`realloc`**. It takes a pointer to the memory block to be deallocated as an argument. After calling **`free`**, the memory block becomes available for reuse.
    
    ```c
    free(ptr);
    ```
    

It's important to note a few things when working with dynamic memory allocation:

- Always check if the memory allocation was successful. **`malloc`**, **`calloc`**, and **`realloc`** return **`NULL`** if memory allocation fails.
- Always free dynamically allocated memory when it's no longer needed to prevent memory leaks.
- Avoid accessing memory after it has been deallocated with **`free`**, as it can lead to undefined behavior.

Here's an example illustrating dynamic memory allocation and deallocation:

```c
#include <stdio.h>
#include <stdlib.h>
int main() {
    // Dynamically allocate memory for an array of 5 integers
    int *ptr = (int *)malloc(5 * sizeof(int));
    if (ptr == NULL) {
        printf("Memory allocation failed\n");
        return 1;
    }

    // Initialize the allocated memory
    for (int i = 0; i < 5; i++) {
        ptr[i] = i + 1;
    }

    // Print the values stored in the array
    printf("Values stored in the array:\n");
    for (int i = 0; i < 5; i++) {
        printf("%d ", ptr[i]);
    }
    printf("\n");

    // Free the dynamically allocated memory
    free(ptr);

    return 0;
}

```

This code dynamically allocates memory for an array of 5 integers using **`malloc`**, initializes the array, prints its values, and then deallocates the memory using **`free`**.