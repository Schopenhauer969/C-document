# ⚙️ C — Complete Guide (Beginner to Advanced)

> A complete, hands-on guide to C — from your first program to pointers, memory management, and multi-file projects used in real production code.

---

## 📚 Table of Contents

1. [Introduction](#1-introduction)
2. [Prerequisites & Setup](#2-prerequisites--setup)
3. [Your First C Program](#3-your-first-c-program)
4. [Variables & Data Types](#4-variables--data-types)
5. [Operators](#5-operators)
6. [Control Flow](#6-control-flow)
7. [Arrays](#7-arrays)
8. [Strings](#8-strings)
9. [Functions](#9-functions)
10. [Pointers](#10-pointers)
11. [Structs & Unions](#11-structs--unions)
12. [Dynamic Memory Allocation](#12-dynamic-memory-allocation)
13. [File I/O](#13-file-io)
14. [Preprocessor Directives](#14-preprocessor-directives)
15. [Multi-File Programs & Header Files](#15-multi-file-programs--header-files)
16. [Command-Line Arguments](#16-command-line-arguments)
17. [Common Pitfalls & Debugging](#17-common-pitfalls--debugging)
18. [Best Practices](#18-best-practices)
19. [Full Example Project](#19-full-example-project)
20. [Resources](#20-resources)

---

## 1. Introduction

C is a low-level, compiled, general-purpose programming language created in 1972. It gives direct control over memory and hardware, making it the foundation for operating systems (Linux, Windows kernels), embedded systems, and most other programming languages' runtimes.

**Key facts:**
- Compiled directly to machine code — no virtual machine or interpreter
- Statically typed — every variable's type is fixed at compile time
- Manual memory management (no garbage collector)
- Extremely fast and close to the hardware
- Current standard: **C17** (with C23 emerging)

---

## 2. Prerequisites & Setup

- No prior coding experience required, though it helps
- A C compiler: **GCC**, **Clang**, or **MSVC** (Windows)
- A code editor: **VS Code**, **CLion**

```bash
# Verify installation (Linux/macOS, using GCC)
gcc --version

# On macOS, GCC is usually an alias for Clang
clang --version
```

**Compiling and running a C program:**

```bash
# Compile hello.c into an executable named "hello"
gcc hello.c -o hello

# Run the compiled program
./hello        # Linux/macOS
hello.exe      # Windows
```

---

## 3. Your First C Program

```c
// hello.c
#include <stdio.h>

int main(void) {
    printf("Hello, World!\n");
    return 0;
}
```

**Breaking it down:**

| Part | Meaning |
|---|---|
| `#include <stdio.h>` | Includes the Standard Input/Output library (needed for `printf`) |
| `int main(void)` | Entry point — every C program starts execution here |
| `printf(...)` | Prints formatted text to the console |
| `return 0;` | Signals successful program completion to the operating system |

```bash
gcc hello.c -o hello
./hello
# Output: Hello, World!
```

---

## 4. Variables & Data Types

```c
#include <stdio.h>

int main(void) {
    // Basic data types
    int age = 25;                // Whole numbers (typically 4 bytes)
    float price = 19.99f;        // Decimal numbers (4 bytes, note the f suffix)
    double preciseValue = 3.14159265359; // Decimal numbers, more precision (8 bytes)
    char grade = 'A';             // A single character (1 byte)
    char isActiveFlag = 1;        // C has no true bool in older standards (0 = false, nonzero = true)

    // Fixed-width integers (recommended for portability — from <stdint.h>)
    // #include <stdint.h>
    // int32_t exact32 = 100000;
    // uint8_t smallUnsigned = 255;

    // Unsigned types (only non-negative values, doubles the positive range)
    unsigned int count = 100;

    // Constants
    const double PI = 3.14159;

    // Printing values with format specifiers
    printf("Age: %d\n", age);           // %d for int
    printf("Price: %.2f\n", price);      // %f for float/double, .2 = 2 decimal places
    printf("Grade: %c\n", grade);        // %c for char
    printf("Pi: %lf\n", preciseValue);   // %lf for double

    // sizeof — check how many bytes a type uses
    printf("Size of int: %zu bytes\n", sizeof(int));
    printf("Size of double: %zu bytes\n", sizeof(double));

    return 0;
}
```

**Boolean type (C99+):**

```c
#include <stdio.h>
#include <stdbool.h> // Required for true bool support

int main(void) {
    bool isActive = true;
    bool isDone = false;

    printf("Is active: %d\n", isActive); // Prints 1 (C has no native bool printf format)
    return 0;
}
```

---

## 5. Operators

```c
#include <stdio.h>

int main(void) {
    // Arithmetic
    printf("%d\n", 10 + 5);   // 15
    printf("%d\n", 10 - 5);   // 5
    printf("%d\n", 10 * 5);   // 50
    printf("%d\n", 10 / 3);   // 3 (integer division truncates!)
    printf("%f\n", 10.0 / 3); // 3.333333
    printf("%d\n", 10 % 3);   // 1 (modulo)

    // Increment/decrement
    int count = 0;
    count++;   // Post-increment
    ++count;   // Pre-increment
    printf("%d\n", count); // 2

    // Comparison
    printf("%d\n", 5 == 5);  // 1 (true)
    printf("%d\n", 5 != 3);  // 1 (true)
    printf("%d\n", 10 > 5);  // 1 (true)

    // Logical
    int a = 1, b = 0;
    printf("%d\n", a && b);  // 0 (AND)
    printf("%d\n", a || b);  // 1 (OR)
    printf("%d\n", !a);       // 0 (NOT)

    // Bitwise operators
    printf("%d\n", 5 & 3);   // 1  (AND)
    printf("%d\n", 5 | 3);   // 7  (OR)
    printf("%d\n", 5 ^ 3);   // 6  (XOR)
    printf("%d\n", ~5);       // -6 (NOT)
    printf("%d\n", 5 << 1);   // 10 (left shift = multiply by 2)
    printf("%d\n", 5 >> 1);   // 2  (right shift = divide by 2)

    // Compound assignment
    int x = 10;
    x += 5;  // x = 15
    x -= 3;  // x = 12
    x *= 2;  // x = 24

    return 0;
}
```

---

## 6. Control Flow

```c
#include <stdio.h>

int main(void) {
    int score = 85;

    // if / else if / else
    if (score >= 90) {
        printf("Grade: A\n");
    } else if (score >= 80) {
        printf("Grade: B\n");
    } else {
        printf("Grade: C or below\n");
    }

    // Ternary operator
    int isPassing = (score >= 60) ? 1 : 0;
    printf("Passing: %d\n", isPassing);

    // switch statement
    int day = 3;
    switch (day) {
        case 1:
            printf("Monday\n");
            break;
        case 2:
            printf("Tuesday\n");
            break;
        default:
            printf("Another day\n");
            break; // Good practice even on the last case
    }

    // for loop
    for (int i = 0; i < 5; i++) {
        printf("Iteration %d\n", i);
    }

    // while loop
    int n = 0;
    while (n < 3) {
        printf("n = %d\n", n);
        n++;
    }

    // do-while loop (runs at least once)
    int m = 0;
    do {
        printf("m = %d\n", m);
        m++;
    } while (m < 3);

    // break and continue
    for (int i = 0; i < 10; i++) {
        if (i == 3) continue; // Skip this iteration
        if (i == 6) break;    // Exit the loop entirely
        printf("%d\n", i);
    }

    return 0;
}
```

---

## 7. Arrays

```c
#include <stdio.h>

int main(void) {
    // Declaring and initializing arrays
    int numbers[5] = {10, 20, 30, 40, 50};
    int zeros[5] = {0}; // All elements initialized to 0

    // Accessing elements (zero-indexed)
    printf("%d\n", numbers[0]); // 10
    printf("%d\n", numbers[4]); // 50

    // Modifying elements
    numbers[0] = 100;

    // Getting array length (only works within the same scope where it's declared!)
    int length = sizeof(numbers) / sizeof(numbers[0]);
    printf("Length: %d\n", length); // 5

    // Looping through an array
    for (int i = 0; i < length; i++) {
        printf("%d ", numbers[i]);
    }
    printf("\n");

    // Multidimensional arrays
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };
    printf("%d\n", matrix[1][2]); // 6 (row 1, column 2)

    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 3; col++) {
            printf("%d ", matrix[row][col]);
        }
        printf("\n");
    }

    // IMPORTANT: C does NOT check array bounds — accessing numbers[10] is undefined
    // behavior (may crash, may silently corrupt memory). Always track your own bounds.

    return 0;
}
```

---

## 8. Strings

In C, strings are simply arrays of `char` terminated by a null byte (`'\0'`).

```c
#include <stdio.h>
#include <string.h>

int main(void) {
    // Declaring strings
    char greeting[20] = "Hello";      // Enough space for "Hello" + null terminator
    char name[] = "Sophea";            // Size automatically inferred

    printf("%s\n", greeting); // %s for strings

    // String length (excludes the null terminator)
    printf("Length: %zu\n", strlen(name)); // 6

    // Concatenation (destination buffer MUST have enough space!)
    char fullGreeting[50] = "Hello, ";
    strcat(fullGreeting, name);
    strcat(fullGreeting, "!");
    printf("%s\n", fullGreeting); // "Hello, Sophea!"

    // Copying strings
    char copy[20];
    strcpy(copy, name);
    printf("%s\n", copy); // "Sophea"

    // Comparing strings (NEVER use == on strings — that compares pointers, not content)
    if (strcmp(name, "Sophea") == 0) {
        printf("Names match!\n");
    }

    // Safer, bounded versions (recommended — prevent buffer overflows)
    char safeCopy[10];
    strncpy(safeCopy, "Hello World", sizeof(safeCopy) - 1);
    safeCopy[sizeof(safeCopy) - 1] = '\0'; // Always manually null-terminate with strncpy

    // Formatted string building
    char message[50];
    snprintf(message, sizeof(message), "%s is %d years old", name, 25);
    printf("%s\n", message); // "Sophea is 25 years old"

    // Looping through a string character by character
    for (int i = 0; name[i] != '\0'; i++) {
        printf("%c", name[i]);
    }
    printf("\n");

    // Reading a line of input safely
    char input[100];
    printf("Enter your name: ");
    fgets(input, sizeof(input), stdin);
    input[strcspn(input, "\n")] = '\0'; // Remove the trailing newline from fgets
    printf("Hello, %s!\n", input);

    return 0;
}
```

**⚠️ Never use `gets()`** — it's removed from modern C standards because it can't limit input size, causing buffer overflows. Always use `fgets()` instead.

---

## 9. Functions

```c
#include <stdio.h>

// Function declaration (prototype) — tells the compiler the signature ahead of time
int add(int a, int b);
void printGreeting(const char *name);
int factorial(int n);

int main(void) {
    printf("%d\n", add(3, 4));       // 7
    printGreeting("Sophea");
    printf("%d\n", factorial(5));     // 120
    return 0;
}

// Function definitions
int add(int a, int b) {
    return a + b;
}

// void function — performs an action, returns nothing
void printGreeting(const char *name) {
    // "const" means this function promises not to modify the string
    printf("Hello, %s!\n", name);
}

// Recursive function
int factorial(int n) {
    if (n <= 1) return 1;          // Base case
    return n * factorial(n - 1);   // Recursive case
}
```

**Passing arrays to functions (arrays decay to pointers):**

```c
#include <stdio.h>

// The array parameter is really a pointer — the size is lost, so pass it separately
void printArray(int arr[], int size) {
    for (int i = 0; i < size; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");
}

int sumArray(int arr[], int size) {
    int total = 0;
    for (int i = 0; i < size; i++) {
        total += arr[i];
    }
    return total;
}

int main(void) {
    int numbers[] = {1, 2, 3, 4, 5};
    int size = sizeof(numbers) / sizeof(numbers[0]);

    printArray(numbers, size);
    printf("Sum: %d\n", sumArray(numbers, size)); // 15

    return 0;
}
```

---

## 10. Pointers

A pointer is a variable that stores the **memory address** of another variable. Pointers are the defining feature of C.

```c
#include <stdio.h>

int main(void) {
    int age = 25;
    int *agePtr = &age; // &age gets the ADDRESS of age; agePtr now points to it

    printf("Value of age: %d\n", age);       // 25
    printf("Address of age: %p\n", (void *)&age); // Some memory address
    printf("Value of agePtr: %p\n", (void *)agePtr); // Same address as above
    printf("Value pointed to by agePtr: %d\n", *agePtr); // 25 — dereferencing with *

    // Modifying a value through its pointer
    *agePtr = 26;
    printf("New value of age: %d\n", age); // 26 — the original variable changed!

    // Pointers and functions — "pass by reference" using pointers
    int x = 5;
    void increment(int *num);
    increment(&x);
    printf("x after increment: %d\n", x); // 6

    // Pointer arithmetic and arrays (arrays and pointers are closely related)
    int numbers[] = {10, 20, 30};
    int *ptr = numbers; // Points to the first element (equivalent to &numbers[0])

    printf("%d\n", *ptr);       // 10
    printf("%d\n", *(ptr + 1)); // 20 — moves forward by one int's worth of memory
    printf("%d\n", ptr[2]);      // 30 — pointer indexing works just like array indexing

    // NULL pointers — represent "points to nothing"
    int *emptyPtr = NULL;
    if (emptyPtr == NULL) {
        printf("Pointer is not initialized\n");
    }

    // Double pointers (a pointer to a pointer)
    int value = 100;
    int *p1 = &value;
    int **p2 = &p1;
    printf("%d\n", **p2); // 100 — dereference twice to reach the original value

    return 0;
}

void increment(int *num) {
    (*num)++; // Dereference, then increment the actual value
}
```

**Key rule:** `&variable` gets an address; `*pointer` dereferences a pointer to get the value it points to.

---

## 11. Structs & Unions

```c
#include <stdio.h>
#include <string.h>

// Defining a struct — groups related data together
struct Person {
    char name[50];
    int age;
    float height;
};

// Using typedef for a cleaner syntax (avoids writing "struct" every time)
typedef struct {
    double x;
    double y;
} Point;

int main(void) {
    // Creating and initializing a struct
    struct Person person1 = {"Sophea", 25, 165.5f};

    printf("%s is %d years old\n", person1.name, person1.age);

    // Modifying struct fields
    person1.age = 26;
    strcpy(person1.name, "Sophea Chan");

    // Using the typedef'd struct
    Point origin = {0.0, 0.0};
    Point p1 = {3.0, 4.0};
    printf("p1: (%.1f, %.1f)\n", p1.x, p1.y);

    // Structs and pointers — use -> to access fields through a pointer
    struct Person *personPtr = &person1;
    printf("%s\n", personPtr->name);   // Shorthand for (*personPtr).name
    personPtr->age = 27;

    // Array of structs
    struct Person people[2] = {
        {"Sophea", 25, 165.5f},
        {"Dara", 30, 175.0f}
    };
    for (int i = 0; i < 2; i++) {
        printf("%s: %d years\n", people[i].name, people[i].age);
    }

    // Nested structs
    struct Address {
        char city[30];
        char country[30];
    };

    struct Employee {
        char name[50];
        struct Address address;
    };

    struct Employee emp = {"Dara", {"Phnom Penh", "Cambodia"}};
    printf("%s lives in %s\n", emp.name, emp.address.city);

    return 0;
}

// Union — like a struct, but all members SHARE the same memory (only one is valid at a time)
union Data {
    int i;
    float f;
    char str[20];
};
```

---

## 12. Dynamic Memory Allocation

Unlike languages with garbage collection, C requires you to manually allocate and free heap memory.

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
    // malloc — allocate raw memory (uninitialized)
    int *numbers = (int *)malloc(5 * sizeof(int));

    if (numbers == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    for (int i = 0; i < 5; i++) {
        numbers[i] = i * 10;
    }

    for (int i = 0; i < 5; i++) {
        printf("%d ", numbers[i]);
    }
    printf("\n");

    free(numbers); // ALWAYS free memory you've allocated — prevents memory leaks
    numbers = NULL;  // Good practice: avoid a "dangling pointer" after freeing

    // calloc — allocate memory AND initialize it to zero
    int *zeroed = (int *)calloc(5, sizeof(int));
    if (zeroed != NULL) {
        printf("%d\n", zeroed[0]); // 0 — guaranteed zero-initialized
        free(zeroed);
    }

    // realloc — resize a previously allocated block
    int *resizable = (int *)malloc(3 * sizeof(int));
    resizable[0] = 1;
    resizable[1] = 2;
    resizable[2] = 3;

    int *bigger = (int *)realloc(resizable, 5 * sizeof(int));
    if (bigger != NULL) {
        resizable = bigger; // realloc may move the block, so reassign the pointer
        resizable[3] = 4;
        resizable[4] = 5;

        for (int i = 0; i < 5; i++) {
            printf("%d ", resizable[i]);
        }
        printf("\n");
    }
    free(resizable);

    return 0;
}
```

**The golden rules of memory management:**
1. Every `malloc`/`calloc`/`realloc` must eventually be matched with exactly one `free`
2. Never use memory after freeing it (a "use-after-free" bug)
3. Never free the same memory twice (a "double free" bug)
4. Always check if allocation returned `NULL` before using the pointer

---

## 13. File I/O

```c
#include <stdio.h>

int main(void) {
    // --- Writing to a file ---
    FILE *file = fopen("notes.txt", "w"); // "w" = write (overwrites existing content)
    if (file == NULL) {
        printf("Error opening file!\n");
        return 1;
    }
    fprintf(file, "Hello, file world!\n");
    fprintf(file, "Second line: %d\n", 42);
    fclose(file); // Always close files when done

    // --- Appending to a file ---
    file = fopen("notes.txt", "a"); // "a" = append
    if (file != NULL) {
        fprintf(file, "Appended line.\n");
        fclose(file);
    }

    // --- Reading a file line by line ---
    file = fopen("notes.txt", "r"); // "r" = read
    if (file != NULL) {
        char line[100];
        while (fgets(line, sizeof(line), file) != NULL) {
            printf("%s", line);
        }
        fclose(file);
    }

    // --- Writing/reading binary data ---
    int numbers[] = {1, 2, 3, 4, 5};
    FILE *binFile = fopen("data.bin", "wb"); // "wb" = write binary
    if (binFile != NULL) {
        fwrite(numbers, sizeof(int), 5, binFile);
        fclose(binFile);
    }

    int readNumbers[5];
    binFile = fopen("data.bin", "rb"); // "rb" = read binary
    if (binFile != NULL) {
        fread(readNumbers, sizeof(int), 5, binFile);
        fclose(binFile);

        for (int i = 0; i < 5; i++) {
            printf("%d ", readNumbers[i]);
        }
        printf("\n");
    }

    return 0;
}
```

---

## 14. Preprocessor Directives

```c
#include <stdio.h>

// #define — creates constants or macros (text substitution before compilation)
#define PI 3.14159
#define MAX_SIZE 100
#define SQUARE(x) ((x) * (x)) // Macro function — note the parentheses for safety!

// Conditional compilation
#define DEBUG_MODE 1

int main(void) {
    printf("PI = %f\n", PI);
    printf("Square of 5: %d\n", SQUARE(5)); // Expands to ((5) * (5))

    #if DEBUG_MODE
        printf("Debug mode is ON\n");
    #else
        printf("Debug mode is OFF\n");
    #endif

    // #ifdef / #ifndef — check if something is defined
    #ifdef MAX_SIZE
        printf("MAX_SIZE is defined as %d\n", MAX_SIZE);
    #endif

    return 0;
}
```

**Include guards** (prevent a header file from being included multiple times):

```c
// myheader.h
#ifndef MYHEADER_H
#define MYHEADER_H

void greet(void);

#endif // MYHEADER_H
```

---

## 15. Multi-File Programs & Header Files

Large C programs are split across multiple `.c` and `.h` files.

```c
// mathutils.h — header file declares WHAT functions exist
#ifndef MATHUTILS_H
#define MATHUTILS_H

int add(int a, int b);
int subtract(int a, int b);

#endif
```

```c
// mathutils.c — source file defines HOW they work
#include "mathutils.h"

int add(int a, int b) {
    return a + b;
}

int subtract(int a, int b) {
    return a - b;
}
```

```c
// main.c
#include <stdio.h>
#include "mathutils.h" // Local header — quotes, not angle brackets

int main(void) {
    printf("%d\n", add(5, 3));       // 8
    printf("%d\n", subtract(5, 3));   // 2
    return 0;
}
```

```bash
# Compiling multiple files together
gcc main.c mathutils.c -o myprogram
./myprogram
```

---

## 16. Command-Line Arguments

```c
#include <stdio.h>

// argc = argument count, argv = argument vector (array of strings)
int main(int argc, char *argv[]) {
    printf("Program name: %s\n", argv[0]);
    printf("Number of arguments: %d\n", argc);

    for (int i = 1; i < argc; i++) {
        printf("Argument %d: %s\n", i, argv[i]);
    }

    return 0;
}
```

```bash
gcc args.c -o args
./args hello world 123
# Output:
# Program name: ./args
# Number of arguments: 4
# Argument 1: hello
# Argument 2: world
# Argument 3: 123
```

---

## 17. Common Pitfalls & Debugging

```c
#include <stdio.h>

int main(void) {
    // ❌ Pitfall 1: Uninitialized variables contain garbage values
    int x; // Don't do this
    // printf("%d\n", x); // Undefined value!
    int y = 0; // ✅ Always initialize

    // ❌ Pitfall 2: Off-by-one errors in loops
    int arr[5] = {1, 2, 3, 4, 5};
    // for (int i = 0; i <= 5; i++) { arr[i]... } // Bug! Goes out of bounds at i=5
    for (int i = 0; i < 5; i++) { /* ✅ Correct: use < not <= */ }

    // ❌ Pitfall 3: Integer division when you meant float division
    int a = 5, b = 2;
    printf("%d\n", a / b);           // 2, not 2.5!
    printf("%f\n", (float)a / b);     // ✅ Cast to get 2.5

    // ❌ Pitfall 4: Comparing floats with ==
    float f1 = 0.1f + 0.2f;
    // if (f1 == 0.3f) { ... } // May be FALSE due to floating-point imprecision!
    if (f1 > 0.29f && f1 < 0.31f) { /* ✅ Use a tolerance range instead */ }

    // ❌ Pitfall 5: Memory leaks (forgetting to free)
    // int *p = malloc(sizeof(int)); // Never freed = leak

    // ❌ Pitfall 6: Dangling pointers (using memory after freeing it)
    // free(p); *p = 5; // Undefined behavior!

    return 0;
}
```

**Debugging tools:**

```bash
# Compile with debug symbols and warnings enabled
gcc -g -Wall -Wextra program.c -o program

# Use gdb (GNU Debugger) to step through code
gdb ./program

# Use Valgrind to detect memory leaks and invalid memory access (Linux)
valgrind --leak-check=full ./program
```

**`-Wall -Wextra`** enables extra compiler warnings — always compile with these flags to catch bugs early.

---

## 18. Best Practices

- ✅ Always check the return value of `malloc()` (and similar) for `NULL` before use
- ✅ Match every `malloc`/`calloc`/`realloc` with exactly one `free`
- ✅ Always initialize variables — never rely on their default garbage value
- ✅ Use `const` for parameters/variables that shouldn't be modified
- ✅ Compile with `-Wall -Wextra` and fix every warning
- ✅ Prefer `fgets()` over `gets()`/`scanf("%s", ...)` for reading strings safely
- ✅ Always check array bounds manually — C does not do this for you
- ✅ Use header guards (`#ifndef`/`#define`/`#endif`) in every `.h` file
- ✅ Keep functions small and focused on a single task
- ✅ Use tools like Valgrind or AddressSanitizer to catch memory bugs

---

## 19. Full Example Project

A simple **Student Grade Manager** combining structs, dynamic memory, and file I/O:

```c
// student.h
#ifndef STUDENT_H
#define STUDENT_H

typedef struct {
    char name[50];
    float grade;
} Student;

Student *createStudents(int count);
void printStudents(Student *students, int count);
float calculateAverage(Student *students, int count);
void freeStudents(Student *students);

#endif
```

```c
// student.c
#include <stdio.h>
#include <stdlib.h>
#include "student.h"

Student *createStudents(int count) {
    Student *students = (Student *)malloc(count * sizeof(Student));
    if (students == NULL) {
        printf("Memory allocation failed!\n");
        exit(1);
    }
    return students;
}

void printStudents(Student *students, int count) {
    for (int i = 0; i < count; i++) {
        printf("%s: %.1f\n", students[i].name, students[i].grade);
    }
}

float calculateAverage(Student *students, int count) {
    float total = 0;
    for (int i = 0; i < count; i++) {
        total += students[i].grade;
    }
    return count > 0 ? total / count : 0;
}

void freeStudents(Student *students) {
    free(students);
}
```

```c
// main.c
#include <stdio.h>
#include <string.h>
#include "student.h"

int main(void) {
    int studentCount = 3;
    Student *students = createStudents(studentCount);

    strcpy(students[0].name, "Sophea");
    students[0].grade = 92.5f;

    strcpy(students[1].name, "Dara");
    students[1].grade = 85.0f;

    strcpy(students[2].name, "Bopha");
    students[2].grade = 78.3f;

    printf("--- Student Grades ---\n");
    printStudents(students, studentCount);

    float average = calculateAverage(students, studentCount);
    printf("\nClass average: %.2f\n", average);

    // Save the report to a file
    FILE *report = fopen("grades_report.txt", "w");
    if (report != NULL) {
        fprintf(report, "--- Student Grades ---\n");
        for (int i = 0; i < studentCount; i++) {
            fprintf(report, "%s: %.1f\n", students[i].name, students[i].grade);
        }
        fprintf(report, "\nClass average: %.2f\n", average);
        fclose(report);
        printf("\nReport saved to grades_report.txt\n");
    }

    freeStudents(students); // Clean up allocated memory
    return 0;
}
```

```bash
# Compile all files together
gcc main.c student.c -o grade_manager -Wall -Wextra

# Run it
./grade_manager
```

---

## 20. Resources

- C reference: `https://en.cppreference.com/w/c`
- GNU C Library manual: `https://www.gnu.org/software/libc/manual/`
- Learn C (interactive): `https://www.learn-c.org/`

---

<p align="center">
  Made with ❤️ for developers learning C.
</p>
