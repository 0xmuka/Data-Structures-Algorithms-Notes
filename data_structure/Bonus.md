## Functions in C Programming

<aside>
✍️ **Functions contribute to code modularity, making programs easier to understand, maintain, and extend.**

</aside>

- **Exploring the Power and Flexibility of Functions in C Programming**
    
    *In programming, a **function** is like a named tool that does a specific job. It helps to keep the code organized by breaking it into smaller, reusable parts. Think of it as a fundamental building block in many programming languages, including C.*
    
- **Functions in programming have some important features:**
    - **Modularity:** Functions help to break down a program into smaller, easier-to-handle parts. Each function does a specific task, making the code clearer and more manageable.
        
        ```c
        // Function to calculate the square of a number
        int square(int num) {
            return num * num;
        }
        ```
        
        - **Explanation:**
            - This function (square) calculates the square of the number passed to it. It's an isolated function that performs a specific task.
        
        ---
        
    - **Reuse:** Once a function is created, you can use it in different parts of the program. This avoids repeating the same code and makes it more efficient.
        
        ```c
        // Function to add two numbers
        int add(int a, int b) {
            return a + b;
        }
        
        int main() {
            int result = add(3, 4); // Calling the add function
            // ...
        }
        ```
        
        - **Explanation:**
            - We can use the add function in multiple places in the program to perform addition instead of repeating the code every time.
        
        ---
        
    - **Abstraction:** Functions hide the details of how they work. When you use a function, you only need to know what it does, not how it achieves it.
        - Example
        
        ```c
        // Function to display a greeting message
        void greet() {
            printf("Hello, welcome!");
        }
        ```
        
        - **Explanation:**
            - The greet function displays a welcome message. It doesn't matter to the part using this function how it works internally; it's enough to know that it provides a welcome message.
        
        ---
        
    - **Parameters:** Functions can take inputs called parameters, allowing them to work with different data each time they are used. Parameters make functions flexible and customizable.
        - Example
        
        ```c
        // Function to multiply two numbers
        int multiply(int x, int y) {
            return x * y;
        }
        ```
        
        - **Explanation:**
            - This multiply function takes two numbers (x and y) as parameters, and the function can be called with different values to perform multiplication on any pair of numbers.
        
        ---
        
    - **Return Values:** Functions can give back a result to the part of the program that called them. This helps in providing feedback or getting a specific output.
        - **Example**
        
        ```c
        // Function to check if a number is even
        int isEven(int num) {
            if (num % 2 == 0) {
                return 1; // True (even)
            } else {
                return 0; // False (odd)
            }
        }
        
        ```
        
        - Explanation:
            - The **`isEven`** function checks whether the number passed to it is even or odd. It returns the value 1 if true (even) and 0 if false (odd).
    
    ---
    
- **Calculating the average of an array using a simple C program. 📊**
    
    ```c
    #include <stdio.h>
    
    int avg(int *marks , int);
    
    int main()
    {
    
        int mark[5] = {10,20,30,40,50},size,average;
    
        size = sizeof(mark)/sizeof(mark[0]);
    
        average = avg(mark,size);
    
        printf("average = %d\n",average);
    
    }
    
    int avg(int array[], int sizeOfAarry)
    {
    
        int i,sum = 0, average = 0;
    
        for ( i = 0; i < sizeOfAarry; i++)
        {
            sum = sum + array[i];
        }
        average = sum / sizeOfAarry;
    
        return average;
        
    
    }
    ```
    
    - **Array Initialization:**
        - Array **`mark`** initialized with values {10, 20, 30, 40, 50}.
    - **Function Declaration and Definition:**
        - Function **`avg`** declared and defined to calculate array average.
        - Parameters: Array (**`marks`**) and size (**`sizeOfArray`**).
    - **Main Function:**
        - Size of array calculated using **`sizeof`**.
        - **`avg`** function called with array and size, result stored in **`average`**.
    - **Average Calculation:**
        - **`avg`** function calculates sum of array elements and computes average.
    - **Output:**
        - Average printed in the main function.
    - **Summary:**
        - Program uses functions for average calculation, enhancing code organization and reusability.
- **Displaying a String Using a Function**
    
    ```c
    #include <stdio.h>
    
    void dispaly(char []);
    
    int main()
    {
    
        char str[] = "Ibrahim";
        
        dispaly(str);
    
    }
    
    void dispaly(char string[])
    {
    
        printf("%s\n",string);
    
    }
    ```
    
    1. **Header and Function Declaration:**
        - The program includes the standard input/output header (**`<stdio.h>`**).
        - Function **`display`** is declared, which takes a character array (**`char[]`**) as a parameter.
    2. **Main Function:**
        - Inside **`main`**, a character array **`str`** is initialized with the value "Ibrahim".
        - The **`display`** function is called with **`str`** as an argument.
    3. **Display Function:**
        - The **`display`** function is defined to print the provided string using **`printf`**.
    
    **Summary:**
    The program showcases a simple function (**`display`**) that takes a character array and prints it. In this example, it displays the string "Ibrahim" from the `
    
- **Utilizing Function Pointers for String Manipulation in C**
    
    ```c
    #include <stdio.h>
    
    void modify(char [], char []);
    
    int main()
    {
        char str1[] = "Ibrahim";
    
        char str2[] = "sallam";
    
        modify(str1,str2);
    }
    
    void modify(char string1[],char string2[])
    {
        int i, length1 = 0, length2 = 0 ;
    
        for ( i = 0; string1[i] != '\0'; i++)
        {
            length1 ++;
        }
    
        printf("length of first string is : %d\n",length1);
       
        for ( i = 0; string2[i] != '\0'; i++)
        {
            length2 ++;
        }
    
        printf("length of last string is : %d\n",length2);
    
        string2[0] = 'S';
    
        printf("length of name is : %d\nyour name is: %s %s\n", length1 + length2,string1,string2);
    }
    ```
    
    ---
    
    > **Pointers are read-only**, meaning they cannot be modified when used to declare a variable, but arrays are read-and-write, which means their values can be changed. So Therefore, the code with a red mark is invalid
    > 
    
    ```c
    #include <stdio.h>
    
    void modify(char [], char []);
    
    int main()
    {
        char str1[] = "Ibrahim";
    
        char str2[] = "sallam";
    
        modify(str1,str2);
    }
    
    void modify(char string1[],char string2[])
    {
        int i, length1 = 0, length2 = 0 ;
    
        for ( i = 0; string1[i] != '\0'; i++)
        {
            length1 ++;
        }
    
        printf("length of first string is : %d\n",length1);
       
        for ( i = 0; string2[i] != '\0'; i++)
        {
            length2 ++;
        }
    
        printf("length of last string is : %d\n",length2);
    
        string2[0] = 'S';
    
        printf("length of name is : %d\nyour name is: %s %s\n", length1 + length2,string1,string2);
    }
    ```
    
    ```c
    #include <stdio.h>
    
    void modify(char [], char []);
    
    int main()
    {
        char *str1 = "Ibrahim";
    
        char *str2 = "sallam";
    
        modify(str1,str2);
    }
    
    void modify(char string1[],char string2[])
    {
        int i, length1 = 0, length2 = 0 ;
    
        for ( i = 0; string1[i] != '\0'; i++)
        {
            length1 ++;
        }
    
        printf("length of first string is : %d\n",length1);
       
        for ( i = 0; string2[i] != '\0'; i++)
        {
            length2 ++;
        }
    
        printf("length of last string is : %d\n",length2);
    
        string2[0] = 'S';
    
        printf("length of name is : %d\nyour name is: %s %s\n", length1 + length2,string1,string2);
    }
    ```
    
- **String Handling in C: Constancy and Modifiability in Function Returns**
    
    
    ```c
    #include <stdio.h>
    
    char *display();
    
    int main() {
        const char *str;
        str = display();
        printf("%s\n", str);
    }
    
    char *display() {
        char *string = "hello";
        return string;
    }
    ```
    
    - **Explanation:**
        - In the first code, the display function returns a pointer to a constant string "hello".
        In main, str is defined as a constant (const) and is used to store the string returned from the display function.
        The "hello" string cannot be modified in this context.
        
    
    ```c
    #include <stdio.h>
    
    char *display();
    
    int main() {
        char *str;
        str = display();
        str[5] = '!';
        printf("%s\n", str);
    }
    char *display() {
        static char string[] = "hello";
        return string;
    }
    ```
    
    - **Explanation:**
        - In the second code, the display function returns a pointer to a local array (static) containing "hello".
        In main, str is defined as a pointer to the returned array, and the sixth character of the string (which holds the value 'o') is modified to be '!'.
        Here, the array returned from the display function can be modified due to the presence of static.
    
    ---
    
    **Difference:**
    
    - **`const`** is used in **`main`** to define **`str`**, meaning **`str`** cannot be modified.
    - **`char *`** is used to define **`string`** in **`display`**, but the pointer points to a constant string, and the string cannot be modified.
    
    ---
    
    **Conclusion:**
    
    - The main difference is in the ability to modify the returned string by the function. In the first code, the string cannot be modified (constant string), while in the second code, it can be modified (local array with **`static`**).
- **Pointer Manipulation in C: Returning and Utilizing Pointers from Functions**
    
    ```c
    #include <stdio.h>
    
    int * returnPointer(int[]);
    
    int main()
    {
    
        int a[] = {1,2,3,4,5},*p;
        returnPointer(a);
        p = returnPointer(a);
        printf("%d\n",*p);
    
    }
    
    int * returnPointer(int *a)
    {
    
        a = a+2;
        return a;
    
    }
    ```
    
    - **Explanation:**
        - The program defines a function **`returnPointer`** that takes an integer array pointer as an argument and returns a modified pointer.
        - In **`main`**, an integer array **`a`** is initialized, and the **`returnPointer`** function is called twice.
        - The first call does not capture the returned pointer, while the second call assigns the returned pointer to the variable **`p`**.
        - The value pointed to by **`p`** is then printed, which should be the third element of the array due to the pointer manipulation in the function.
        - The **`returnPointer`** function increments the provided pointer by 2 positions and returns the modified pointer.
        - The headline and explanation highlight the key concept of working with pointers in functions, emphasizing returning pointers and utilizing them in the main program.
- **Utilizing Pointers to Functions in C: Summing Numbers with a Function Pointer**
    
    ```c
    #include <stdio.h>
    
    int sum(int, int);
    
    int main() {
        int result = 0;
        int (*ptr)(int, int) = sum;
        result = ptr(221, 3);
        printf("Result: %d\n", result);
    }
    
    int sum(int a, int b) {
        return a + b;
    }
    ```
    
    - **Explanation:**
        - The program demonstrates the use of a function pointer (**`ptr`**) to point to the **`sum`** function.
        - The function pointer is declared as **`int (*ptr)(int, int)`**, indicating that it can point to a function that takes two integers as parameters and returns an integer.
        - The function pointer **`ptr`** is then assigned to point to the **`sum`** function.
        - The **`ptr`** is used to call the **`sum`** function with arguments 221 and 3, and the result is stored in the variable **`result`**.
        - Finally, the result is printed using **`printf`**.
        - This example highlights the flexibility and versatility of function pointers in C, allowing for dynamic function calls.
- **Callback Function using Function Pointer in C**
    
    ```c
    #include <stdio.h>
    
    void sum(int a, int b) {
        printf("sum = %d\n", a + b);
    }
    
    void sub(int x, int y) {
        printf("sub = %d\n", x - y);
    }
    
    void display(void (*ptr)(int, int)) {
        ptr(5, 1);
    }
    
    int main() {
        display(sum);
        display(sub);
    }
    ```
    
    - **Explanation:**
        - The program demonstrates the concept of callback functions in C using function pointers.
        - Two functions, **`sum`** and **`sub`**, are defined to perform addition and subtraction operations.
        - The **`display`** function takes a function pointer (**`ptr`**) as a parameter and calls the function it points to with arguments 5 and 1.
        - In the **`main`** function, **`display`** is called twice with different functions (**`sum`** and **`sub`**) as arguments, showcasing the ability to dynamically choose operations at runtime.
        - This example highlights the use of callback functions and function pointers to enable dynamic behavior in C programming.
- **Application of Function Pointer in C**
    
    ```c
    #include <stdio.h>
    
    /*
    These lines declare the prototypes of four functions (add, sub, mult, and div) 
    that perform basic arithmetic operations.
    The functions take two integer parameters and do not return anything (void).
    */
    
    void add(int a, int b)
    {
         printf("%d",a+b);
    }
    void sub(int a, int b)
    {
         printf("%d",a-b);
    }
    void mult(int a, int b)
    {
         printf("%d",a*b);
    }
    void div(int a, int b)
    {
         printf("%d",a/b);
    }
    
    /*
    
    */
    
    int main()
    {
        void(*ptr[10])(int,int)={add,sub,mult,div};
        int ch, a,b;
        printf("Enter choise: ");
        scanf("%d",&ch);
        if(ch <= 3){
        printf("enter a,b\n");
        scanf("%d%d",&a,&b);
        }
        else
        {
    
            printf("inter nubmer between 0:3\n");
            return 1;
        }
    
        //(*ptr[ch])(a,b);
        switch (ch)
        {
        case 0:
            add(a,b);
            break;
        case 1:
            sub(a,b);
            break;
            case 2:
            mult(a,b);
            break;
            case 3:
            div(a,b);
            break;  
        default:
            printf("enter valid number btween 0 : 4\n");
            break;
        }
    
    }
    ```
    
    - **Explain:**
        - An array of function pointers (**`ptr`**) is declared to store the addresses of the arithmetic functions.The user is prompted to enter a choice for the arithmetic operation.If the choice is valid (between 0 and 3), the user is prompted to enter two numbers (**`a`** and **`b`**).The program then uses a switch statement to call the appropriate arithmetic function based on the user's choice.If the choice is not valid, an error message is displayed, and the program returns an error code (**`1`**).The main function returns **`0`** to indicate successful execution.
            
            In summary, this program creates a simple calculator that allows the user to choose an arithmetic operation, input two numbers, and then displays the result of the chosen operation. The use of function pointers and a switch statement makes the code modular and easy to extend with additional operations.
            
- **Using Variadic Functions in C to Print Numbers**
    
    ```c
    #include <stdio.h>
    #include <stdarg.h>
    
    // Function to print a variable number of integers
    void printNumbers(int count, ...)
    {
        va_list countPtr;
        va_start(countPtr, count); // Initialize the va_list with the variable arguments and the count parameter
        int i;
    
        // Loop through the provided count and print each integer argument
        for (i = 0; i < count; i++)
        {
            printf("%d\n", va_arg(countPtr, int)); // Access the next integer argument and print it
        }
    
        va_end(countPtr); // Clean up the va_list
    }
    
    // Main function
    int main()
    {
        // Call the printNumbers function with five integer arguments
        printNumbers(5, 1, 2, 3, 4, 5);
    
        return 0; // Return 0 to indicate successful program execution
    }
    ```
    
    - **Explanation:**
        - Header Files: The code includes necessary header files for standard input/output (stdio.h) and variable arguments (stdarg.h).
        - Function Definition (printNumbers): The printNumbers function is defined to take a variable number of integer arguments using the ellipsis (...). It uses the va_list, va_start, and va_arg macros to iterate through the variable arguments and print each one.
        - Function Call (printNumbers): In the main function, printNumbers is called with a count of 5 and the integers 1, 2, 3, 4, and 5 as arguments.
        - Return Statement: The main function includes a return 0; statement to indicate successful program execution to the operating system.
        
- **Customizable Variadic Function in C for Formatted Number Printing**
    
    ```c
    **#include <stdio.h>
    #include <stdarg.h>
    
    void printNumbers(int count, ...)
    {
        char str[20];
        int i;
        va_list countPtr;
        va_start(countPtr, count);
    
        for ( i = 0; i < count*3; i+=3)
        {
            str[i] = '%';
            str[i+1] = 'd';
            str[i+2] = ',';
        }
        str[i]='\n';
        str[i+1]='\0';
    
        vprintf(str,countPtr);
        va_end(countPtr);
    }
    
    int main()
    {
    
        printNumbers(5,    1,2,3,4,5);
    
    }**
    ```
    
    **Explanation:**
    
    The provided C code introduces a **`printNumbers`** function that utilizes variable arguments to print a specified number of integers in a customizable format. Here's a breakdown of the code:
    
    1. **Header Files:**
        - The code includes standard input/output (**`stdio.h`**) and variable argument handling (**`stdarg.h`**) header files.
    2. **Function Definition (`printNumbers`):**
        - The function takes an integer **`count`** and a variable number of integer arguments using the ellipsis (**`...`**).
        - It also initializes a character array **`str`** with a size of 20 to construct a format string.
        - A loop builds the format string to include **`%d`** for each integer argument, separated by commas.
        - The loop terminates with a newline character and null terminator to complete the format string.
        - The **`vprintf`** function is then used to print the formatted string, with variable arguments provided by **`va_list countPtr`**.
    3. **Function Call (`printNumbers`):**
        - In the **`main`** function, **`printNumbers`** is called with a count of 5 and the integers 1, 2, 3, 4, and 5 as arguments.
    4. **Output:**
        - The function prints the numbers in the specified format, separating them with commas and ending with a newline.
    
    **Note:** This code provides flexibility by allowing the user to define the format of the printed numbers, making it a customizable and reusable variadic function.
    
- **Custom `printf` Implementation in C with Variable Arguments"**
    
    ```c
    #include <stdio.h>
    #include <stdarg.h>
    
    void _printf(char *format, ...)
    {
    
        va_list argPtr;
    
        va_start(argPtr,format);
    
        vprintf(format, argPtr);
        
        va_end(argPtr);
    
    }
    int main()
    {
    
        _printf("%s,%d,%c,%i,%x\n","ibrahim",32,'c',3,0xf3);
    
    }
    ```
    
    **Explanation:**
    
    The provided C code defines a simplified version of the **`printf`** function named **`_printf`**. This custom function takes a format string and a variable number of arguments, utilizing the **`<stdarg.h>`** library for handling variable arguments. Here's a breakdown of the code:
    
    1. **Header Files:**
        - The code includes standard input/output (**`stdio.h`**) and variable argument handling (**`stdarg.h`**) header files.
    2. **Function Definition (`_printf`):**
        - The **`_printf`** function takes a format string (**`char *format`**) and a variable number of arguments using the ellipsis (**`...`**).
        - It initializes a **`va_list`** named **`argPtr`** using **`va_start`** to access the variable arguments.
        - The function then calls **`vprintf`** to print the formatted output based on the provided format string and variable arguments.
        - **`va_end`** is used to clean up the **`va_list`** after its use.
    3. **Function Call (`_printf`):**
        - In the **`main`** function, **`_printf`** is called with a format string **`"%s,%d,%c,%i,%x"`** and corresponding arguments: **`"ibrahim"`**, **`32`**, **`'c'`**, **`3`**, and **`0xf3`**.
    4. **Output:**
        - The **`_printf`** function prints the formatted output based on the provided format string and arguments, resulting in the output: "ibrahim,32,c,3,f3".
    
    **Note:** This code demonstrates a basic implementation of a variable argument function resembling **`printf`**. The format specifier in the format string determines the type and formatting of the output.
    

---

## printf in C Programming

<aside>
✍️ **The Printf Project is part of the ALX software engineering program that focuses on creating and implementing the printf function in C programming. 
This function is vital as it is extensively used to output data to the console.
By successfully completing this project, participants gain invaluable experience and a deep understanding of how printf works, ultimately enhancing their overall programming skills.**

</aside>

- **Format Specifiers in C**
    
    Format specifiers define the type of data to be printed on standard output. You need to use format specifiers whether you're printing formatted output with `printf()` or  accepting input with `scanf()`.
    
    Some of the % specifiers that you can use in ANSI C are as follows:
    
    | SPECIFIER | USED FOR |
    | --- | --- |
    | %c | a single character |
    | %s | a string |
    | %hi | short (signed) |
    | %hu | short (unsigned) |
    | %Lf | long double |
    | %n | prints nothing |
    | %d | a decimal integer (assumes base 10) |
    | %i | a decimal integer (detects the base automatically) |
    | %o | an octal (base 8) integer |
    | %x | a hexadecimal (base 16) integer |
    | %p | an address (or pointer) |
    | %f | a floating point number for floats |
    | %u | int unsigned decimal |
    | %e | a floating point number in scientific notation |
    | %E | a floating point number in scientific notation |
    | %% | the % symbol |
    - %d or %i: Used to print integers
    - %f: Used to print floating point numbers
    - %c: Used to print characters
    - %s: Used to print strings
    - %x or %X: Used to print hexadecimal numbers
    - %p: Used to print pointers
    - %%: Used to print the % character
    
    # **Examples:**
    
    ### **`%c` single character format specifier:**
    
    ```c
    #include <stdio.h>
    
    int main() {
      char first_ch = 'f';
      printf("%c\n", first_ch);
      return 0;
    }
    ```
    
    **Output:**
    
    ```
    f
    ```
    
    **Note**: It is important to note that the format specifiers must be preceded by the % symbol, and must be followed by the appropriate argument.
    
- **Implementing the printf() function**
    
    In this section, we will go over the process of implementing the printf() function. We will start by creating the function prototype and then move on to writing the function body. The function body will handle the different types of format specifiers and handle variable arguments using va_list, va_start and va_end macros.
    
    ### Overview:
    
    The implementation of the printf() function starts by creating the function prototype, that declares the function name, return type, and the number and type of its parameters. The next step is to write the function body, which handles the different types of format specifiers and variable arguments.
    
- **Creating the function prototype**
    
    The first step in implementing the printf() function is to create the function prototype. The function prototype is a statement that declares the function’s name, return type, and the number and type of its parameters. The prototype for the printf() function is as follows:
    
    ```c
    int my_printf(const char *format, ...);
    ```
    
    In this prototype, the function name is “my_printf”, the return type is int, and the function takes two parameters, the first one is a pointer to a constant character and the second one is variable arguments (indicated by the “…”).
    
- **Writing the function body**
    
    Once the prototype is created, we can move on to writing the function body. The function body is where the actual code for the function is written. The main task of the function body is to handle the different types of format specifiers and to output the appropriate text.
    
- **Handling the different types of format specifiers**
    
    The printf() function must be able to handle all the different types of format specifiers that can be used. 
    
    To do this, we can use a switch statement to check for each format specifier and handle it accordingly.
    
     For example, if the format specifier is %d, we can use the printf() function to print an integer. If the format specifier is %s, we can use the printf() function to print a string. 
    
    To do this, we must check the format string for the format specifier and take the appropriate action.
    
- **Handling variable arguments**
    
    The printf() function takes variable arguments, which means that the number of arguments passed to the function can vary.
    
     To handle variable arguments, we can use the va_list, va_start, and va_end macros.
    
     These macros are used to create a list of variable arguments, start the list, and end the list, respectively. 
    
    This allows us to handle any number of arguments passed to the function. And these macros comes from the library header **`<stdarg.h**>`.
    
- **What is `<stdarg.h>`?**
    
    The `[<stdarg.h>](https://en.wikipedia.org/wiki/Stdarg.h)` header file is a C standard library header that is used for handling variable arguments in functions. It defines a set of macros and type definitions that allow a function to accept a variable number of arguments. These macros and type definitions are used to create a list of variable arguments, start the list, and end the list.
    
    The `<stdarg.h>` header file contains the following macros:
    
    - **va_list**: This is a type definition that represents a list of variable arguments.
    - **va_start**: This macro initializes a va_list object, making it ready to access the variable arguments.
    - **va_arg**: This macro retrieves the next argument from the va_list.
    - **va_end**: This macro is used to clean up the va_list object after the variable arguments have been processed.
    
    These macros are used together to handle variable arguments in a function. The va_start macro is used to initialize a va_list object and start the list of variable arguments, the va_arg macro is used to retrieve the next argument from the list, and the va_end macro is used to clean up the va_list object after the variable arguments have been processed.
    
    In the case of writing the printf() function, `<stdarg.h>` is included in the header file to make use of the va_list, va_start, and va_end macros in handling variable arguments in the function.
    
    As a developer, it’s important to keep in mind that the implementation of the printf() function is not a straightforward task. It requires a good understanding of C programming and the intricacies of the printf() function. Additionally, it’s essential to thoroughly test and debug the code to ensure that it works correctly.
    
- **code demonstrates how to handle variable arguments**
    
    ```c
    va_list args;
    va_start(args, format);
    int x = va_arg(args, int);
    va_end(args);
    ```
    
- **actual code to create your custom print function**
    
    ```c
    #include <stdio.h>
    #include <stdarg.h>int myprintf(const char *format, ...)
    {
    va_list args;
    va_start(args, format);int count = 0;
    while (*format != '\0')
    {
    if (*format != '%')
    {
    putchar(*format);
    count++;
    }
    else
    {
    // Handle format specifiers
    switch (*++format)
    {
    case 'd':
    count += fprintf(stdout, "%d", va_arg(args, int));
    break;
    case 'c':
    count += fprintf(stdout, "%c", va_arg(args, char));
    break;
    case 's':
    count += fprintf(stdout, "%s", va_arg(args, char *));
    break;
    case 'f':
    count += fprintf(stdout, "%f", va_arg(args, double));
    break;
    default:
    // Handle unknown format specifiers
    putchar('%');
    putchar(*format);
    count += 2;
    break;
    }
    }
    format++;
    }va_end(args);
    return count;
    }
    ```
    
    This is just one example of how you can write your own printf() function in C. It is important to note that this function is not as robust as the standard printf() function and may not handle all edge cases. However, it is a good starting point for understanding how the printf() function works and how to write your own version of it.
    
- **Basic C Program using write() to Print a String**
    
    ```c
    #include <stdio.h>
    #include <unistd.h>
    #include <string.h>
    
    int main() {
        // This line includes necessary header files for standard input/output, system calls (write), and string functions.
    
        const char *format = "Ibrahim is The End\n";
        // This line declares a constant character pointer named 'format' and initializes it with the string "Ibrahim is The End\n".
    
        write(1, format, strlen(format));
        // This line uses the write() system call to write the contents of the 'format' string to the file descriptor 1 (stdout). The third argument is the length of the string.
    
        return 0;
        // This line indicates that the program has executed successfully by returning 0 to the operating system.
    }
    ```
    
    **Explanation:**
    
    1. **`#include <stdio.h>`**: Includes the standard input/output header file for functions like **`printf`**.
    2. **`#include <unistd.h>`**: Includes the necessary header file for the **`write`** system call.
    3. **`#include <string.h>`**: Includes the string manipulation functions like **`strlen`**.
    4. **`int main() { ... }`**: Defines the main function, the entry point of the program.
    5. **`const char *format = "Ibrahim is The End\n";`**: Declares a constant character pointer named 'format' and initializes it with the string "Ibrahim is The End\n".
    6. **`write(1, format, strlen(format));`**: Uses the **`write()`** system call to write the contents of the 'format' string to the file descriptor 1 (stdout). The third argument is the length of the string obtained using **`strlen(format)`**.
    7. **`return 0;`**: Indicates successful execution by returning 0 to the operating system.
    
    **Execution:**
    The program prints the message "Ibrahim is The End\n" to the standard output using the low-level **`write()`** function, showcasing a simple example of string output in C without relying on the higher-level **`printf`** function.
    

### Mapping:

- **Testing the function with different inputs**
    
    Testing is an important step when writing your own printf() function, as it ensures that the function works correctly. 
    
    It is important to test the function with different inputs, including different format specifiers and arguments.
    
     For example, you can test the function by passing different integers, floating-point numbers, characters, strings, hexadecimal numbers, and pointers as arguments. 
    
    Additionally, you can also test the function with different combinations of format specifiers and arguments to ensure that it handles them correctly.
    
    - **Example**
        - Here is an example of how you can test the function:
    
    ```c
    int main(void)
    {
    int age = 25;
    myprintf("My name is %s and I am %d years old.\n", "Snehasish", age);
    double pi = 3.14;
    myprintf("The value of pi is %.2f.\n", pi);
    // Print a date and time.
    myprintf("%s %s\n", "Today is", __DATE__);
    myprintf("%s %s\n", "The time is", __TIME__);// Print a list of numbers.
    int numbers[] = {1, 2, 3, 4, 5};
    for (int i = 0; i < sizeof(numbers) / sizeof(numbers[0]); i++)
    {
    myprintf("%d\n", numbers[i]);
    }// Print a table of data.
    myprintf("| Name | Age | Occupation |\n");
    myprintf("| Snehasish | 25 | AI Engineer |\n");
    myprintf("| Alice | 30 | Software Engineer |\n");
    }
    ```
    

Relation is such that each element of a given set (the domain of the function) is associated with an element of another set (the range of the function).
