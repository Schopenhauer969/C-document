# C Programming — Beginner to Advanced

> A complete C programming guide from **Beginner → Intermediate → Advanced**, with examples, explanations, and practical programs.
> មគ្គុទ្ទេសក៍ C Programming ពេញលេញ ចាប់ពី **កម្រិតដំបូង → មធ្យម → កម្រិតខ្ពស់**។

---

## 📚 Table of Contents

* [1. What is C?](#1-what-is-c)
* [2. Features of C](#2-features-of-c)
* [3. Install C Compiler](#3-install-c-compiler)
* [4. Your First C Program](#4-your-first-c-program)
* [5. C Program Structure](#5-c-program-structure)
* [6. Comments](#6-comments)
* [7. Variables](#7-variables)
* [8. Data Types](#8-data-types)
* [9. Constants](#9-constants)
* [10. Input and Output](#10-input-and-output)
* [11. Format Specifiers](#11-format-specifiers)
* [12. Operators](#12-operators)
* [13. Type Casting](#13-type-casting)
* [14. Conditional Statements](#14-conditional-statements)
* [15. Loops](#15-loops)
* [16. Functions](#16-functions)
* [17. Scope](#17-scope)
* [18. Arrays](#18-arrays)
* [19. Strings](#19-strings)
* [20. Pointers](#20-pointers)
* [21. Pointer and Array](#21-pointer-and-array)
* [22. Functions and Pointers](#22-functions-and-pointers)
* [23. Dynamic Memory Allocation](#23-dynamic-memory-allocation)
* [24. Structures](#24-structures)
* [25. Unions](#25-unions)
* [26. Enumerations](#26-enumerations)
* [27. typedef](#27-typedef)
* [28. File Handling](#28-file-handling)
* [29. Preprocessor](#29-preprocessor)
* [30. Header Files](#30-header-files)
* [31. Command-Line Arguments](#31-command-line-arguments)
* [32. Bitwise Operators](#32-bitwise-operators)
* [33. Function Pointers](#33-function-pointers)
* [34. Recursion](#34-recursion)
* [35. const, static, extern, volatile](#35-const-static-extern-volatile)
* [36. Memory Layout](#36-memory-layout)
* [37. Error Handling](#37-error-handling)
* [38. Modular Programming](#38-modular-programming)
* [39. Linked List](#39-linked-list)
* [40. Stack](#40-stack)
* [41. Queue](#41-queue)
* [42. Binary Search Tree](#42-binary-search-tree)
* [43. Sorting](#43-sorting)
* [44. Searching](#44-searching)
* [45. Makefile](#45-makefile)
* [46. Debugging](#46-debugging)
* [47. Common Mistakes](#47-common-mistakes)
* [48. Best Practices](#48-best-practices)
* [49. Projects](#49-projects)
* [50. Learning Roadmap](#50-learning-roadmap)

---

# 1. What is C?

## English

C is a general-purpose, procedural programming language created by **Dennis Ritchie** at Bell Labs.

C is widely used for:

* Operating systems
* Embedded systems
* Device drivers
* Compilers
* Databases
* Networking
* System programming
* High-performance applications

C gives programmers direct control over memory and hardware.

## Khmer

C គឺជា **General-Purpose Programming Language** ដែលត្រូវបានបង្កើតឡើងដោយ **Dennis Ritchie** នៅ Bell Labs។

C ត្រូវបានប្រើសម្រាប់៖

* Operating System
* Embedded System
* Device Driver
* Compiler
* Database
* Networking
* System Programming
* High-performance applications

ចំណុចសំខាន់របស់ C គឺអាចឱ្យ Programmer គ្រប់គ្រង **Memory** និង **Hardware** បានយ៉ាងជិតស្និទ្ធ។

---

# 2. Features of C

### English

Important features:

1. Simple
2. Fast
3. Procedural
4. Portable
5. Low-level memory access
6. Structured programming
7. Efficient
8. Supports pointers
9. Supports dynamic memory
10. Suitable for system programming

### Khmer

លក្ខណៈសំខាន់ៗរបស់ C៖

1. ងាយស្រួលរៀន
2. លឿន
3. Procedural Programming
4. អាច Run លើ Platform ជាច្រើន
5. អាចគ្រប់គ្រង Memory
6. មាន Structure ច្បាស់លាស់
7. មាន Performance ខ្ពស់
8. មាន Pointer
9. មាន Dynamic Memory Allocation
10. សាកសមសម្រាប់ System Programming

---

# 3. Install C Compiler

You need a C compiler.

Popular choices:

* GCC
* Clang
* MSVC

For Linux:

```bash
sudo apt update
sudo apt install build-essential
```

Check GCC:

```bash
gcc --version
```

Compile a program:

```bash
gcc main.c -o main
```

Run:

```bash
./main
```

Windows with MinGW/GCC:

```bash
gcc main.c -o main.exe
main.exe
```

---

# 4. Your First C Program

Create:

```text
main.c
```

Code:

```c
#include <stdio.h>

int main(void)
{
    printf("Hello, World!\n");

    return 0;
}
```

## Explanation

```c
#include <stdio.h>
```

Includes the standard input/output library.

```c
int main(void)
```

The program starts execution from `main()`.

```c
printf("Hello, World!\n");
```

Prints text to the terminal.

```c
return 0;
```

Indicates successful program execution.

## Khmer

`#include <stdio.h>` គឺ Import Standard Input/Output Library។

`main()` គឺជា Function ដែលកម្មវិធីចាប់ផ្តើមដំណើរការ។

`printf()` ប្រើសម្រាប់បង្ហាញ Output។

`return 0` មានន័យថា Program បានបញ្ចប់ដោយជោគជ័យ។

---

# 5. C Program Structure

Basic structure:

```c
#include <stdio.h>

int main(void)
{
    // Code goes here

    return 0;
}
```

Example:

```c
#include <stdio.h>

int main(void)
{
    int age = 20;

    printf("Age: %d\n", age);

    return 0;
}
```

### Khmer

Program C ទូទៅមាន៖

```text
Header
   ↓
main()
   ↓
Statements
   ↓
return
```

---

# 6. Comments

Comments are ignored by the compiler.

## Single-line comment

```c
// This is a comment
```

## Multi-line comment

```c
/*
   This is
   a multi-line comment
*/
```

Example:

```c
#include <stdio.h>

int main(void)
{
    // Store user's age
    int age = 20;

    /*
       Print the age
       to the terminal.
    */
    printf("%d\n", age);

    return 0;
}
```

### Khmer

Comment គឺជាអត្ថបទសម្រាប់ពន្យល់ Code ហើយ Compiler មិនយកទៅ Execute ទេ។

---

# 7. Variables

A variable stores data in memory.

Syntax:

```c
data_type variable_name = value;
```

Example:

```c
#include <stdio.h>

int main(void)
{
    int age = 20;
    float height = 1.75f;
    char grade = 'A';

    printf("Age: %d\n", age);
    printf("Height: %.2f\n", height);
    printf("Grade: %c\n", grade);

    return 0;
}
```

### Khmer

Variable គឺជាកន្លែងមួយនៅក្នុង Memory សម្រាប់រក្សាទុក Data។

ឧទាហរណ៍៖

```c
int age = 20;
```

មានន័យថា បង្កើត Variable `age` ប្រភេទ `int` និងមានតម្លៃ `20`។

---

# 8. Data Types

Common C data types:

| Type     | Purpose              |
| -------- | -------------------- |
| `char`   | Character            |
| `int`    | Integer              |
| `float`  | Decimal              |
| `double` | More precise decimal |
| `void`   | No value             |

Example:

```c
#include <stdio.h>

int main(void)
{
    char letter = 'A';
    int age = 20;
    float price = 10.5f;
    double pi = 3.1415926535;

    printf("Letter: %c\n", letter);
    printf("Age: %d\n", age);
    printf("Price: %.2f\n", price);
    printf("Pi: %.10f\n", pi);

    return 0;
}
```

---

# 9. Constants

A constant cannot normally be modified after initialization.

## Using `const`

```c
#include <stdio.h>

int main(void)
{
    const double PI = 3.141592653589793;

    printf("PI = %.15f\n", PI);

    return 0;
}
```

You cannot do:

```c
PI = 10;
```

### Khmer

`const` ប្រើសម្រាប់បង្កើតតម្លៃដែលមិនគួរត្រូវបានកែប្រែ។

---

# 10. Input and Output

## Output

```c
printf("Hello\n");
```

## Input

Use `scanf()`.

```c
#include <stdio.h>

int main(void)
{
    int age;

    printf("Enter your age: ");

    if (scanf("%d", &age) == 1)
    {
        printf("You are %d years old.\n", age);
    }

    return 0;
}
```

Important:

```c
&age
```

passes the address of `age` to `scanf()`.

### Khmer

`scanf()` ប្រើសម្រាប់ទទួល Input ពី User។

`&age` គឺ Address របស់ Variable `age` ដែល `scanf()` ត្រូវការដើម្បីដាក់តម្លៃចូលទៅក្នុង Memory។

---

# 11. Format Specifiers

Common format specifiers:

| Specifier | Type                |
| --------- | ------------------- |
| `%d`      | `int`               |
| `%u`      | `unsigned int`      |
| `%ld`     | `long`              |
| `%f`      | `float` in `printf` |
| `%lf`     | `double` in `scanf` |
| `%c`      | `char`              |
| `%s`      | String              |
| `%p`      | Pointer address     |
| `%zu`     | `size_t`            |

Example:

```c
#include <stdio.h>

int main(void)
{
    int number = 100;
    double price = 25.50;
    char grade = 'A';

    printf("Number: %d\n", number);
    printf("Price: %.2f\n", price);
    printf("Grade: %c\n", grade);

    return 0;
}
```

---

# 12. Operators

## Arithmetic Operators

```text
+   Addition
-   Subtraction
*   Multiplication
/   Division
%   Modulus
```

Example:

```c
#include <stdio.h>

int main(void)
{
    int a = 10;
    int b = 3;

    printf("Addition: %d\n", a + b);
    printf("Subtraction: %d\n", a - b);
    printf("Multiplication: %d\n", a * b);
    printf("Division: %d\n", a / b);
    printf("Modulus: %d\n", a % b);

    return 0;
}
```

## Comparison Operators

```text
==    Equal
!=    Not equal
>     Greater than
<     Less than
>=    Greater or equal
<=    Less or equal
```

## Logical Operators

```text
&&    AND
||    OR
!     NOT
```

---

# 13. Type Casting

Type casting converts one type into another.

Example:

```c
#include <stdio.h>

int main(void)
{
    int a = 10;
    int b = 3;

    double result = (double)a / b;

    printf("Result: %.2f\n", result);

    return 0;
}
```

Output:

```text
Result: 3.33
```

Without casting:

```c
double result = a / b;
```

The integer division happens first.

### Khmer

Type Casting គឺការបម្លែង Data Type មួយទៅ Data Type មួយទៀត។

---

# 14. Conditional Statements

## if

```c
#include <stdio.h>

int main(void)
{
    int age = 20;

    if (age >= 18)
    {
        printf("Adult\n");
    }

    return 0;
}
```

## if / else

```c
#include <stdio.h>

int main(void)
{
    int age = 16;

    if (age >= 18)
    {
        printf("Adult\n");
    }
    else
    {
        printf("Minor\n");
    }

    return 0;
}
```

## else if

```c
#include <stdio.h>

int main(void)
{
    int score = 85;

    if (score >= 90)
    {
        printf("Grade A\n");
    }
    else if (score >= 80)
    {
        printf("Grade B\n");
    }
    else if (score >= 70)
    {
        printf("Grade C\n");
    }
    else
    {
        printf("Grade F\n");
    }

    return 0;
}
```

---

# 15. Loops

Loops repeat code.

## for loop

```c
#include <stdio.h>

int main(void)
{
    for (int i = 1; i <= 5; i++)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

## while loop

```c
#include <stdio.h>

int main(void)
{
    int i = 1;

    while (i <= 5)
    {
        printf("%d\n", i);
        i++;
    }

    return 0;
}
```

## do-while

```c
#include <stdio.h>

int main(void)
{
    int i = 1;

    do
    {
        printf("%d\n", i);
        i++;
    }
    while (i <= 5);

    return 0;
}
```

## break

```c
#include <stdio.h>

int main(void)
{
    for (int i = 1; i <= 10; i++)
    {
        if (i == 5)
        {
            break;
        }

        printf("%d\n", i);
    }

    return 0;
}
```

## continue

```c
#include <stdio.h>

int main(void)
{
    for (int i = 1; i <= 5; i++)
    {
        if (i == 3)
        {
            continue;
        }

        printf("%d\n", i);
    }

    return 0;
}
```

### Khmer

Loop ប្រើសម្រាប់ Execute Code ម្តងហើយម្តងទៀត។

---

# 16. Functions

Functions allow us to organize reusable code.

```c
#include <stdio.h>

int add(int a, int b)
{
    return a + b;
}

int main(void)
{
    int result = add(10, 20);

    printf("Result: %d\n", result);

    return 0;
}
```

## Function with no return value

```c
#include <stdio.h>

void sayHello(void)
{
    printf("Hello!\n");
}

int main(void)
{
    sayHello();

    return 0;
}
```

### Khmer

Function គឺជាប្លុក Code ដែលអាចយកមកប្រើឡើងវិញបាន។

---

# 17. Scope

Scope determines where a variable can be accessed.

```c
#include <stdio.h>

int globalValue = 100;

int main(void)
{
    int localValue = 50;

    printf("Global: %d\n", globalValue);
    printf("Local: %d\n", localValue);

    return 0;
}
```

A variable declared inside a function normally belongs to that function's local scope.

---

# 18. Arrays

An array stores multiple values of the same type.

```c
#include <stdio.h>

int main(void)
{
    int numbers[5] = {10, 20, 30, 40, 50};

    for (int i = 0; i < 5; i++)
    {
        printf("%d\n", numbers[i]);
    }

    return 0;
}
```

Array indexing starts at `0`.

```text
numbers[0]
numbers[1]
numbers[2]
numbers[3]
numbers[4]
```

### Khmer

Array គឺជាកន្លែងសម្រាប់រក្សាទុក Data ច្រើនដែលមាន Type ដូចគ្នា។

---

# 19. Strings

C does not have a built-in `string` type.

Strings are arrays of characters ending with `'\0'`.

```c
#include <stdio.h>

int main(void)
{
    char name[] = "Heng";

    printf("Name: %s\n", name);

    return 0;
}
```

The actual memory contains:

```text
H e n g \0
```

## String functions

Include:

```c
#include <string.h>
```

Example:

```c
#include <stdio.h>
#include <string.h>

int main(void)
{
    char firstName[50] = "Heng";
    char lastName[50] = "Developer";

    printf("Length: %zu\n", strlen(firstName));

    strcat(firstName, " ");
    strcat(firstName, lastName);

    printf("Full name: %s\n", firstName);

    return 0;
}
```

Common functions:

```text
strlen()
strcpy()
strncpy()
strcat()
strcmp()
```

> Be careful with buffer sizes when using string functions.

---

# 20. Pointers

Pointers are one of the most important concepts in C.

A pointer stores the address of another variable.

```c
#include <stdio.h>

int main(void)
{
    int number = 100;

    int *ptr = &number;

    printf("Value: %d\n", number);
    printf("Address: %p\n", (void *)&number);
    printf("Pointer: %p\n", (void *)ptr);
    printf("Value through pointer: %d\n", *ptr);

    return 0;
}
```

Important operators:

```text
&   Address-of
*   Dereference
```

### Khmer

Pointer គឺជា Variable ដែលរក្សាទុក **Memory Address** របស់ Variable ផ្សេងទៀត។

ឧទាហរណ៍៖

```c
int number = 100;
int *ptr = &number;
```

`ptr` រក្សាទុក Address របស់ `number`។

`*ptr` មានន័យថា ចូលទៅយក Value នៅ Address នោះ។

---

# 21. Pointer and Array

An array name often converts to a pointer to its first element when used in an expression.

```c
#include <stdio.h>

int main(void)
{
    int numbers[] = {10, 20, 30};

    int *ptr = numbers;

    for (int i = 0; i < 3; i++)
    {
        printf("%d\n", *(ptr + i));
    }

    return 0;
}
```

These are equivalent for an array:

```c
numbers[i]
```

and:

```c
*(numbers + i)
```

---

# 22. Functions and Pointers

Pointers allow functions to modify variables in the caller.

```c
#include <stdio.h>

void swap(int *a, int *b)
{
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main(void)
{
    int x = 10;
    int y = 20;

    printf("Before: x=%d, y=%d\n", x, y);

    swap(&x, &y);

    printf("After: x=%d, y=%d\n", x, y);

    return 0;
}
```

### Khmer

C ប្រើ Pass-by-Value ជាចម្បង។

បើចង់ឱ្យ Function កែ Variable របស់ Caller យើងអាចបញ្ជូន Address តាម Pointer។

---

# 23. Dynamic Memory Allocation

Dynamic memory is allocated at runtime.

Include:

```c
#include <stdlib.h>
```

Functions:

```text
malloc()
calloc()
realloc()
free()
```

## malloc

```c
#include <stdio.h>
#include <stdlib.h>

int main(void)
{
    int n = 5;

    int *numbers = malloc((size_t)n * sizeof *numbers);

    if (numbers == NULL)
    {
        printf("Memory allocation failed.\n");
        return 1;
    }

    for (int i = 0; i < n; i++)
    {
        numbers[i] = (i + 1) * 10;
    }

    for (int i = 0; i < n; i++)
    {
        printf("%d\n", numbers[i]);
    }

    free(numbers);

    return 0;
}
```

### Important

Always release dynamically allocated memory:

```c
free(numbers);
```

### Khmer

Dynamic Memory Allocation គឺការស្នើសុំ Memory នៅពេល Program កំពុង Run។

បន្ទាប់ពីប្រើរួច ត្រូវ:

```c
free(pointer);
```

ដើម្បីជៀសវាង Memory Leak។

---

# 24. Structures

A structure groups different data types.

```c
#include <stdio.h>

struct Student
{
    char name[50];
    int age;
    double score;
};

int main(void)
{
    struct Student student = {
        "Heng",
        20,
        95.5
    };

    printf("Name: %s\n", student.name);
    printf("Age: %d\n", student.age);
    printf("Score: %.2f\n", student.score);

    return 0;
}
```

### Khmer

`struct` អនុញ្ញាតឱ្យយើងបញ្ចូល Data Types ខុសៗគ្នាទៅក្នុង Object មួយ។

---

# 25. Unions

A union stores different members in the same memory location.

```c
#include <stdio.h>

union Data
{
    int number;
    float decimal;
    char letter;
};

int main(void)
{
    union Data data;

    data.number = 100;

    printf("Number: %d\n", data.number);

    data.decimal = 25.5f;

    printf("Decimal: %.2f\n", data.decimal);

    return 0;
}
```

### Important

Only one member should generally be treated as the active value at a time.

### Khmer

`union` ចែក Memory តែមួយឱ្យ Members ទាំងអស់។

វាខុសពី `struct` ដែល Member នីមួយៗមាន Storage របស់ខ្លួន។

---

# 26. Enumerations

`enum` creates named integer constants.

```c
#include <stdio.h>

enum Day
{
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY
};

int main(void)
{
    enum Day today = WEDNESDAY;

    printf("Today value: %d\n", today);

    return 0;
}
```

---

# 27. typedef

`typedef` creates an alternative name for a type.

```c
#include <stdio.h>

typedef unsigned int uint;

typedef struct
{
    char name[50];
    int age;
} Student;

int main(void)
{
    uint number = 100;

    Student student = {
        "Heng",
        20
    };

    printf("Number: %u\n", number);
    printf("Name: %s\n", student.name);
    printf("Age: %d\n", student.age);

    return 0;
}
```

---

# 28. File Handling

C can read and write files using `FILE`.

## Write a file

```c
#include <stdio.h>

int main(void)
{
    FILE *file = fopen("data.txt", "w");

    if (file == NULL)
    {
        perror("fopen");
        return 1;
    }

    fprintf(file, "Hello from C!\n");
    fprintf(file, "This is a file.\n");

    fclose(file);

    return 0;
}
```

## Read a file

```c
#include <stdio.h>

int main(void)
{
    FILE *file = fopen("data.txt", "r");

    if (file == NULL)
    {
        perror("fopen");
        return 1;
    }

    char buffer[256];

    while (fgets(buffer, sizeof buffer, file) != NULL)
    {
        printf("%s", buffer);
    }

    fclose(file);

    return 0;
}
```

Common modes:

```text
"r"   Read
"w"   Write
"a"   Append
"rb"  Read binary
"wb"  Write binary
```

---

# 29. Preprocessor

The preprocessor runs before compilation.

## #define

```c
#include <stdio.h>

#define MAX_USERS 100

int main(void)
{
    printf("Maximum users: %d\n", MAX_USERS);

    return 0;
}
```

## Conditional compilation

```c
#include <stdio.h>

#define DEBUG

int main(void)
{
#ifdef DEBUG
    printf("Debug mode enabled.\n");
#endif

    printf("Program running.\n");

    return 0;
}
```

---

# 30. Header Files

Header files contain declarations that can be shared between source files.

Project:

```text
project/
├── main.c
├── math_utils.c
└── math_utils.h
```

## math_utils.h

```c
#ifndef MATH_UTILS_H
#define MATH_UTILS_H

int add(int a, int b);
int subtract(int a, int b);

#endif
```

## math_utils.c

```c
#include "math_utils.h"

int add(int a, int b)
{
    return a + b;
}

int subtract(int a, int b)
{
    return a - b;
}
```

## main.c

```c
#include <stdio.h>
#include "math_utils.h"

int main(void)
{
    printf("Add: %d\n", add(10, 5));
    printf("Subtract: %d\n", subtract(10, 5));

    return 0;
}
```

Compile:

```bash
gcc main.c math_utils.c -o app
```

Run:

```bash
./app
```

### Khmer

Header file ជួយឱ្យយើងបែងចែក Project ជា Module ដើម្បីងាយស្រួល Maintenance។

---

# 31. Command-Line Arguments

C supports command-line arguments using:

```c
int main(int argc, char *argv[])
```

Example:

```c
#include <stdio.h>

int main(int argc, char *argv[])
{
    printf("Argument count: %d\n", argc);

    for (int i = 0; i < argc; i++)
    {
        printf("argv[%d] = %s\n", i, argv[i]);
    }

    return 0;
}
```

Compile:

```bash
gcc main.c -o app
```

Run:

```bash
./app hello world
```

---

# 32. Bitwise Operators

Bitwise operators work with individual bits.

```text
&   AND
|   OR
^   XOR
~   NOT
<<  Left shift
>>  Right shift
```

Example:

```c
#include <stdio.h>

int main(void)
{
    unsigned int a = 5;
    unsigned int b = 3;

    printf("AND: %u\n", a & b);
    printf("OR: %u\n", a | b);
    printf("XOR: %u\n", a ^ b);
    printf("Left shift: %u\n", a << 1);
    printf("Right shift: %u\n", a >> 1);

    return 0;
}
```

### Binary representation

```text
5 = 0101
3 = 0011

5 & 3 = 0001
5 | 3 = 0111
5 ^ 3 = 0110
```

### Khmer

Bitwise Operator ដំណើរការលើ **Bits** នៃ Integer។

វាសំខាន់សម្រាប់៖

* Embedded systems
* Hardware
* Networking
* Performance
* Flags

---

# 33. Function Pointers

A function pointer stores the address of a function.

```c
#include <stdio.h>

int add(int a, int b)
{
    return a + b;
}

int multiply(int a, int b)
{
    return a * b;
}

int calculate(int a, int b, int (*operation)(int, int))
{
    return operation(a, b);
}

int main(void)
{
    printf("Add: %d\n", calculate(5, 3, add));
    printf("Multiply: %d\n", calculate(5, 3, multiply));

    return 0;
}
```

This is useful for:

* Callbacks
* Event systems
* Generic algorithms
* State machines
* Sorting functions

---

# 34. Recursion

Recursion means a function calls itself.

Example: factorial.

```c
#include <stdio.h>

unsigned long long factorial(unsigned int n)
{
    if (n == 0)
    {
        return 1;
    }

    return n * factorial(n - 1);
}

int main(void)
{
    printf("5! = %llu\n", factorial(5));

    return 0;
}
```

Flow:

```text
factorial(5)
    ↓
5 × factorial(4)
    ↓
4 × factorial(3)
    ↓
3 × factorial(2)
    ↓
2 × factorial(1)
    ↓
1
```

### Khmer

Recursion គឺ Function ហៅខ្លួនឯង។

ត្រូវមាន **Base Case** ដើម្បីបញ្ឈប់ Recursion។

---

# 35. const, static, extern, volatile

## const

Prevents modification through that identifier.

```c
const int MAX = 100;
```

## static

A local static variable keeps its value between function calls.

```c
#include <stdio.h>

void counter(void)
{
    static int count = 0;

    count++;

    printf("Count: %d\n", count);
}

int main(void)
{
    counter();
    counter();
    counter();

    return 0;
}
```

Output:

```text
Count: 1
Count: 2
Count: 3
```

## extern

Used to declare an object or function defined elsewhere.

### counter.c

```c
int counter = 100;
```

### main.c

```c
#include <stdio.h>

extern int counter;

int main(void)
{
    printf("%d\n", counter);

    return 0;
}
```

Compile:

```bash
gcc main.c counter.c -o app
```

## volatile

`volatile` tells the compiler that the object's value may change for reasons outside the normal program flow.

Example:

```c
volatile int hardware_status;
```

Commonly relevant in:

* Embedded systems
* Memory-mapped hardware
* Signal-related code

> `volatile` is not a replacement for atomic operations or synchronization.

---

# 36. Memory Layout

A typical C process contains areas such as:

```text
+----------------------+
|       Stack          |
+----------------------+
|       Heap           |
+----------------------+
|       Data           |
+----------------------+
|       BSS            |
+----------------------+
|       Text/Code      |
+----------------------+
```

Typical concepts:

### Stack

Used for:

* Local variables
* Function calls
* Function parameters

### Heap

Used for:

```c
malloc()
calloc()
realloc()
```

### Data

Usually contains initialized global/static objects.

### BSS

Usually contains zero-initialized or uninitialized global/static objects.

### Text

Contains executable program code.

> Exact memory layout depends on the operating system, compiler, linker, and executable format.

---

# 37. Error Handling

C does not provide exceptions like Java or Python.

Common techniques include:

* Return values
* `errno`
* `perror()`
* `strerror()`

Example:

```c
#include <stdio.h>

int divide(int a, int b, int *result)
{
    if (b == 0)
    {
        return 0;
    }

    *result = a / b;

    return 1;
}

int main(void)
{
    int result;

    if (!divide(10, 2, &result))
    {
        printf("Division failed.\n");
        return 1;
    }

    printf("Result: %d\n", result);

    return 0;
}
```

File error:

```c
#include <stdio.h>

int main(void)
{
    FILE *file = fopen("missing.txt", "r");

    if (file == NULL)
    {
        perror("fopen");
        return 1;
    }

    fclose(file);

    return 0;
}
```

---

# 38. Modular Programming

Large applications should be divided into modules.

Example:

```text
calculator/
├── include/
│   └── calculator.h
├── src/
│   ├── calculator.c
│   └── main.c
└── Makefile
```

## calculator.h

```c
#ifndef CALCULATOR_H
#define CALCULATOR_H

int add(int a, int b);
int subtract(int a, int b);
int multiply(int a, int b);

#endif
```

## calculator.c

```c
#include "calculator.h"

int add(int a, int b)
{
    return a + b;
}

int subtract(int a, int b)
{
    return a - b;
}

int multiply(int a, int b)
{
    return a * b;
}
```

## main.c

```c
#include <stdio.h>
#include "calculator.h"

int main(void)
{
    printf("Add: %d\n", add(10, 5));
    printf("Subtract: %d\n", subtract(10, 5));
    printf("Multiply: %d\n", multiply(10, 5));

    return 0;
}
```

Compile:

```bash
gcc -Wall -Wextra -std=c17 src/main.c src/calculator.c -Iinclude -o calculator
```

---

# 39. Linked List

A linked list consists of nodes connected through pointers.

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Node
{
    int data;
    struct Node *next;
} Node;

int main(void)
{
    Node *first = malloc(sizeof *first);
    Node *second = malloc(sizeof *second);

    if (first == NULL || second == NULL)
    {
        free(first);
        free(second);

        return 1;
    }

    first->data = 10;
    first->next = second;

    second->data = 20;
    second->next = NULL;

    Node *current = first;

    while (current != NULL)
    {
        printf("%d\n", current->data);
        current = current->next;
    }

    free(second);
    free(first);

    return 0;
}
```

Structure:

```text
[10 | next] ---> [20 | NULL]
```

### Khmer

Linked List គឺជា Data Structure ដែល Node នីមួយៗមាន៖

```text
Data
Pointer ទៅ Node បន្ទាប់
```

---

# 40. Stack

Stack follows:

```text
LIFO
Last In, First Out
```

Example implementation:

```c
#include <stdio.h>

#define MAX 100

typedef struct
{
    int data[MAX];
    int top;
} Stack;

void initStack(Stack *stack)
{
    stack->top = -1;
}

int isEmpty(const Stack *stack)
{
    return stack->top == -1;
}

int isFull(const Stack *stack)
{
    return stack->top == MAX - 1;
}

int push(Stack *stack, int value)
{
    if (isFull(stack))
    {
        return 0;
    }

    stack->data[++stack->top] = value;

    return 1;
}

int pop(Stack *stack, int *value)
{
    if (isEmpty(stack))
    {
        return 0;
    }

    *value = stack->data[stack->top--];

    return 1;
}

int main(void)
{
    Stack stack;
    int value;

    initStack(&stack);

    push(&stack, 10);
    push(&stack, 20);
    push(&stack, 30);

    while (pop(&stack, &value))
    {
        printf("%d\n", value);
    }

    return 0;
}
```

Output:

```text
30
20
10
```

---

# 41. Queue

Queue follows:

```text
FIFO
First In, First Out
```

Example:

```c
#include <stdio.h>

#define MAX 5

typedef struct
{
    int data[MAX];
    int front;
    int rear;
} Queue;

void initQueue(Queue *queue)
{
    queue->front = 0;
    queue->rear = 0;
}

int isEmpty(const Queue *queue)
{
    return queue->front == queue->rear;
}

int isFull(const Queue *queue)
{
    return queue->rear == MAX;
}

int enqueue(Queue *queue, int value)
{
    if (isFull(queue))
    {
        return 0;
    }

    queue->data[queue->rear++] = value;

    return 1;
}

int dequeue(Queue *queue, int *value)
{
    if (isEmpty(queue))
    {
        return 0;
    }

    *value = queue->data[queue->front++];

    return 1;
}

int main(void)
{
    Queue queue;
    int value;

    initQueue(&queue);

    enqueue(&queue, 10);
    enqueue(&queue, 20);
    enqueue(&queue, 30);

    while (dequeue(&queue, &value))
    {
        printf("%d\n", value);
    }

    return 0;
}
```

---

# 42. Binary Search Tree

A Binary Search Tree follows:

```text
Left  <  Root  <  Right
```

Example:

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct Node
{
    int data;
    struct Node *left;
    struct Node *right;
} Node;

Node *createNode(int value)
{
    Node *node = malloc(sizeof *node);

    if (node == NULL)
    {
        return NULL;
    }

    node->data = value;
    node->left = NULL;
    node->right = NULL;

    return node;
}

Node *insert(Node *root, int value)
{
    if (root == NULL)
    {
        return createNode(value);
    }

    if (value < root->data)
    {
        root->left = insert(root->left, value);
    }
    else if (value > root->data)
    {
        root->right = insert(root->right, value);
    }

    return root;
}

void inorder(const Node *root)
{
    if (root == NULL)
    {
        return;
    }

    inorder(root->left);
    printf("%d ", root->data);
    inorder(root->right);
}

void freeTree(Node *root)
{
    if (root == NULL)
    {
        return;
    }

    freeTree(root->left);
    freeTree(root->right);

    free(root);
}

int main(void)
{
    Node *root = NULL;

    root = insert(root, 50);
    root = insert(root, 30);
    root = insert(root, 70);
    root = insert(root, 20);
    root = insert(root, 40);

    inorder(root);

    printf("\n");

    freeTree(root);

    return 0;
}
```

Output:

```text
20 30 40 50 70
```

---

# 43. Sorting

## Bubble Sort

```c
#include <stdio.h>

void bubbleSort(int array[], size_t size)
{
    for (size_t i = 0; i < size; i++)
    {
        int swapped = 0;

        for (size_t j = 0; j + 1 < size - i; j++)
        {
            if (array[j] > array[j + 1])
            {
                int temp = array[j];

                array[j] = array[j + 1];
                array[j + 1] = temp;

                swapped = 1;
            }
        }

        if (!swapped)
        {
            break;
        }
    }
}

int main(void)
{
    int numbers[] = {5, 2, 8, 1, 3};

    size_t size = sizeof numbers / sizeof numbers[0];

    bubbleSort(numbers, size);

    for (size_t i = 0; i < size; i++)
    {
        printf("%d ", numbers[i]);
    }

    printf("\n");

    return 0;
}
```

Complexity:

```text
Average: O(n²)
Worst:   O(n²)
Best:    O(n)
```

---

# 44. Searching

## Linear Search

```c
#include <stdio.h>

int linearSearch(
    const int array[],
    size_t size,
    int target
)
{
    for (size_t i = 0; i < size; i++)
    {
        if (array[i] == target)
        {
            return (int)i;
        }
    }

    return -1;
}

int main(void)
{
    int numbers[] = {10, 20, 30, 40, 50};

    size_t size = sizeof numbers / sizeof numbers[0];

    int index = linearSearch(numbers, size, 30);

    if (index != -1)
    {
        printf("Found at index %d\n", index);
    }
    else
    {
        printf("Not found\n");
    }

    return 0;
}
```

Time complexity:

```text
O(n)
```

---

# 45. Makefile

A Makefile helps automate compilation.

Example project:

```text
project/
├── include/
│   └── calculator.h
├── src/
│   ├── calculator.c
│   └── main.c
└── Makefile
```

Makefile:

```makefile
CC = gcc

CFLAGS = -Wall -Wextra -std=c17 -Iinclude

TARGET = calculator

SRC = src/main.c src/calculator.c

$(TARGET): $(SRC)
	$(CC) $(CFLAGS) $(SRC) -o $(TARGET)

clean:
	rm -f $(TARGET)
```

Run:

```bash
make
```

Clean:

```bash
make clean
```

### Windows

The `rm` command may not be available in standard Windows Command Prompt. You can use a Windows-compatible build setup or adapt the `clean` target for your environment.

---

# 46. Debugging

Compile with warnings:

```bash
gcc -Wall -Wextra -Wpedantic -std=c17 main.c -o app
```

Warnings are extremely useful.

For debugging with GCC/GDB:

```bash
gcc -g -Wall -Wextra -std=c17 main.c -o app
```

Run GDB:

```bash
gdb ./app
```

Useful commands:

```text
break main
run
next
step
print variable
continue
quit
```

Example:

```text
(gdb) break main
(gdb) run
(gdb) next
(gdb) print age
```

---

# 47. Common Mistakes

## 1. Using an uninitialized variable

Bad:

```c
int number;

printf("%d\n", number);
```

Good:

```c
int number = 0;

printf("%d\n", number);
```

---

## 2. Forgetting `&` in scanf

Wrong:

```c
int age;

scanf("%d", age);
```

Correct:

```c
int age;

scanf("%d", &age);
```

---

## 3. Buffer overflow

Dangerous:

```c
char name[10];

scanf("%s", name);
```

A long input can exceed the buffer.

Safer approach:

```c
char name[10];

if (scanf("%9s", name) == 1)
{
    printf("%s\n", name);
}
```

For more robust line input, prefer `fgets()`:

```c
#include <stdio.h>
#include <string.h>

int main(void)
{
    char name[100];

    printf("Enter your name: ");

    if (fgets(name, sizeof name, stdin) != NULL)
    {
        name[strcspn(name, "\n")] = '\0';

        printf("Hello, %s\n", name);
    }

    return 0;
}
```

---

## 4. Forgetting free()

Bad:

```c
int *numbers = malloc(10 * sizeof *numbers);
```

Good:

```c
int *numbers = malloc(10 * sizeof *numbers);

if (numbers != NULL)
{
    /* use memory */

    free(numbers);
}
```

---

## 5. Use-after-free

Bad:

```c
int *ptr = malloc(sizeof *ptr);

*ptr = 10;

free(ptr);

printf("%d\n", *ptr);
```

After `free()`, the pointer must not be dereferenced.

Better:

```c
int *ptr = malloc(sizeof *ptr);

if (ptr != NULL)
{
    *ptr = 10;

    printf("%d\n", *ptr);

    free(ptr);
    ptr = NULL;
}
```

---

## 6. Memory leak

Bad:

```c
int *ptr = malloc(sizeof *ptr);

*ptr = 100;

/* forgot free */
```

Good:

```c
int *ptr = malloc(sizeof *ptr);

if (ptr != NULL)
{
    *ptr = 100;

    free(ptr);
}
```

---

# 48. Best Practices

## 1. Compile with warnings

Use:

```bash
gcc -Wall -Wextra -Wpedantic -std=c17 main.c -o app
```

## 2. Use meaningful names

Bad:

```c
int x;
```

Better:

```c
int studentAge;
```

## 3. Keep functions small

Bad:

```text
One huge main()
```

Better:

```text
main()
 ├── readInput()
 ├── calculate()
 ├── validate()
 └── displayResult()
```

## 4. Check allocation

Always check:

```c
if (ptr == NULL)
{
    /* handle error */
}
```

## 5. Free dynamic memory

Every successful allocation should have an appropriate ownership plan and eventual release.

## 6. Initialize variables

Prefer:

```c
int count = 0;
```

instead of:

```c
int count;
```

when initialization is needed.

## 7. Avoid global variables when unnecessary

Prefer passing data through function parameters.

## 8. Use `const`

Example:

```c
void printArray(const int array[], size_t size)
{
    for (size_t i = 0; i < size; i++)
    {
        printf("%d\n", array[i]);
    }
}
```

This communicates that the function does not modify the array elements.

---

# 49. Projects

After learning the fundamentals, build projects.

## Beginner Projects

### 1. Calculator

Features:

```text
Addition
Subtraction
Multiplication
Division
```

### 2. Number Guessing Game

Features:

```text
Random number
User input
Attempts
Win/Lose
```

### 3. Temperature Converter

```text
Celsius → Fahrenheit
Fahrenheit → Celsius
```

### 4. Student Grade System

```text
Name
Age
Score
Grade
Average
```

---

# Intermediate Projects

## 5. Contact Management System

Features:

```text
Add contact
View contacts
Search contact
Update contact
Delete contact
```

Use:

```text
struct
array
functions
file handling
```

---

## 6. Bank Management System

Features:

```text
Create account
Deposit
Withdraw
Balance
Transaction history
```

Use:

```text
struct
file handling
functions
validation
```

---

## 7. Inventory Management System

Features:

```text
Add product
Update product
Delete product
Search product
Stock quantity
Price
Save to file
```

---

# Advanced Projects

## 8. Mini Database

Implement:

```text
Insert
Select
Update
Delete
Search
File persistence
```

---

## 9. HTTP Server

Learn:

```text
Sockets
TCP
HTTP
Request parsing
Response handling
```

---

## 10. Shell

Build a small command shell supporting:

```text
cd
pwd
echo
exit
```

Advanced topics:

```text
processes
pipes
fork
exec
signals
```

> These operating-system APIs are platform-specific. POSIX examples are commonly used on Linux/Unix systems.

---

# 50. Learning Roadmap

## Level 1 — Beginner

Learn:

```text
C syntax
Variables
Data types
Operators
if / else
switch
Loops
Functions
Arrays
Strings
```

Goal:

```text
Build small console programs
```

---

## Level 2 — Intermediate

Learn:

```text
Pointers
Structures
Enums
typedef
File handling
Dynamic memory
Header files
Multiple source files
```

Goal:

```text
Build real applications
```

---

## Level 3 — Advanced

Learn:

```text
Function pointers
Bitwise operations
Memory management
Data structures
Algorithms
Preprocessor
Build systems
Debugging
```

Goal:

```text
Write maintainable and efficient C programs
```

---

## Level 4 — Systems Programming

Learn:

```text
Operating systems
Processes
Threads
Sockets
Networking
System calls
Memory management
Concurrency
Embedded programming
```

Goal:

```text
Build low-level and high-performance software
```

---

# ⭐ Important C Concepts to Master

If you want to become strong in C, focus heavily on these:

```text
1. Variables
2. Functions
3. Arrays
4. Strings
5. Pointers
6. Pointer arithmetic
7. Structures
8. Dynamic memory
9. File handling
10. Header files
11. Modular programming
12. Data structures
13. Algorithms
14. Debugging
15. Memory safety
```

The most important concept is:

```text
POINTERS + MEMORY
```

Understanding these two concepts makes advanced C much easier.

---

# 🧠 C Mental Model

Think about C like this:

```text
Program
   │
   ├── Variables
   │      │
   │      └── Memory
   │
   ├── Functions
   │      │
   │      └── Logic
   │
   ├── Pointers
   │      │
   │      └── Addresses
   │
   ├── Structures
   │      │
   │      └── Data organization
   │
   └── Files
          │
          └── Persistent data
```

### Khmer

អាចយល់ C តាមគំនិតសំខាន់ៗ៖

```text
Variable
   ↓
រក្សាទុក Data ក្នុង Memory

Pointer
   ↓
រក្សាទុក Address

Function
   ↓
រៀបចំ Logic

Struct
   ↓
រៀបចំ Data

malloc/free
   ↓
គ្រប់គ្រង Dynamic Memory

File
   ↓
រក្សាទុក Data រយៈពេលវែង
```

---

# 🔥 Example: Complete Student Management Program

The following combines several concepts:

* `struct`
* Functions
* Arrays
* Input
* Searching
* Loops

```c
#include <stdio.h>
#include <string.h>

#define MAX_STUDENTS 100
#define NAME_SIZE 50

typedef struct
{
    int id;
    char name[NAME_SIZE];
    double score;
} Student;

void addStudent(Student students[], int *count)
{
    if (*count >= MAX_STUDENTS)
    {
        printf("Student limit reached.\n");
        return;
    }

    Student *student = &students[*count];

    printf("Enter ID: ");

    if (scanf("%d", &student->id) != 1)
    {
        printf("Invalid ID.\n");
        return;
    }

    getchar();

    printf("Enter name: ");

    if (fgets(student->name, sizeof student->name, stdin) == NULL)
    {
        printf("Failed to read name.\n");
        return;
    }

    student->name[strcspn(student->name, "\n")] = '\0';

    printf("Enter score: ");

    if (scanf("%lf", &student->score) != 1)
    {
        printf("Invalid score.\n");
        return;
    }

    (*count)++;

    printf("Student added successfully.\n");
}

void displayStudents(
    const Student students[],
    int count
)
{
    if (count == 0)
    {
        printf("No students found.\n");
        return;
    }

    printf("\n===== Students =====\n");

    for (int i = 0; i < count; i++)
    {
        printf(
            "ID: %d | Name: %s | Score: %.2f\n",
            students[i].id,
            students[i].name,
            students[i].score
        );
    }
}

int findStudent(
    const Student students[],
    int count,
    int id
)
{
    for (int i = 0; i < count; i++)
    {
        if (students[i].id == id)
        {
            return i;
        }
    }

    return -1;
}

int main(void)
{
    Student students[MAX_STUDENTS];

    int count = 0;
    int choice;

    while (1)
    {
        printf("\n===== Student Management =====\n");
        printf("1. Add Student\n");
        printf("2. Display Students\n");
        printf("3. Search Student\n");
        printf("4. Exit\n");
        printf("Choose: ");

        if (scanf("%d", &choice) != 1)
        {
            printf("Invalid input.\n");

            int ch;

            while ((ch = getchar()) != '\n' && ch != EOF)
            {
                /* discard invalid input */
            }

            continue;
        }

        switch (choice)
        {
            case 1:
                addStudent(students, &count);
                break;

            case 2:
                displayStudents(students, count);
                break;

            case 3:
            {
                int id;

                printf("Enter ID: ");

                if (scanf("%d", &id) != 1)
                {
                    printf("Invalid ID.\n");
                    break;
                }

                int index = findStudent(
                    students,
                    count,
                    id
                );

                if (index >= 0)
                {
                    printf(
                        "Found: %s | Score: %.2f\n",
                        students[index].name,
                        students[index].score
                    );
                }
                else
                {
                    printf("Student not found.\n");
                }

                break;
            }

            case 4:
                printf("Goodbye!\n");
                return 0;

            default:
                printf("Invalid choice.\n");
        }
    }
}
```

---

# 🏆 Recommended Compilation

For learning, compile with strong warnings:

```bash
gcc -Wall -Wextra -Wpedantic -std=c17 main.c -o app
```

Run:

### Linux/macOS

```bash
./app
```

### Windows

```bash
app.exe
```

---

# 📌 Recommended C Project Structure

For larger applications:

```text
my-c-project/
│
├── README.md
│
├── include/
│   ├── student.h
│   └── database.h
│
├── src/
│   ├── main.c
│   ├── student.c
│   └── database.c
│
├── tests/
│   └── test_student.c
│
├── data/
│   └── students.dat
│
├── Makefile
│
└── .gitignore
```

---

# 🧹 Example `.gitignore`

```gitignore
# Compiled files
*.o
*.obj
*.exe

# Executables
app
main

# Debug files
*.dSYM/

# IDE files
.vscode/
.idea/

# Build directory
build/

# Temporary files
*.tmp
```

---

# 📖 Useful C Standard Libraries

| Header        | Purpose                                |
| ------------- | -------------------------------------- |
| `<stdio.h>`   | Input/output                           |
| `<stdlib.h>`  | Memory, conversions, process utilities |
| `<string.h>`  | String operations                      |
| `<stdbool.h>` | Boolean type                           |
| `<stdint.h>`  | Fixed-width integer types              |
| `<stddef.h>`  | `size_t`, `ptrdiff_t`, etc.            |
| `<ctype.h>`   | Character classification               |
| `<math.h>`    | Mathematical functions                 |
| `<time.h>`    | Date/time                              |
| `<errno.h>`   | Error reporting                        |
| `<assert.h>`  | Assertions                             |
| `<limits.h>`  | Integer limits                         |
| `<float.h>`   | Floating-point limits                  |

Example:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <stdbool.h>
#include <stdint.h>

int main(void)
{
    bool active = true;
    int32_t number = 100;

    char text[] = "C Programming";

    printf("Active: %d\n", active);
    printf("Number: %d\n", number);
    printf("Text: %s\n", text);

    return 0;
}
```

---

# 🎯 Final Learning Path

```text
                    C PROGRAMMING
                         │
                         ▼
                  ┌─────────────┐
                  │   Syntax    │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │ Variables   │
                  │ Data Types  │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │ Conditions  │
                  │   Loops     │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │  Functions  │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │   Arrays    │
                  │   Strings   │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │  Pointers   │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │    Struct   │
                  │    Enum     │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │   Memory    │
                  │ malloc/free │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │ File System │
                  │   Modules   │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │ Data Struct │
                  │  Algorithms │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │ Debugging   │
                  │ Makefiles   │
                  └──────┬──────┘
                         ▼
                  ┌─────────────┐
                  │   SYSTEM    │
                  │ PROGRAMMING │
                  └─────────────┘
```

---

# 🚀 Conclusion

C is one of the best languages for understanding how computers actually work.

If you master:

```text
Variables
↓
Functions
↓
Arrays
↓
Strings
↓
Pointers
↓
Memory
↓
Structures
↓
Files
↓
Data Structures
↓
Algorithms
↓
Debugging
↓
System Programming
```

you will have a strong foundation for learning:

```text
C++
Rust
Operating Systems
Embedded Systems
Linux
Networking
Compilers
Game Engines
Cybersecurity
Computer Architecture
```

## Khmer Summary

C គឺជាភាសាដ៏សំខាន់មួយសម្រាប់អ្នកដែលចង់យល់ពីរបៀបដែល Computer និង Memory ដំណើរការ។

គួររៀនតាមលំដាប់៖

```text
Syntax
→ Variable
→ Data Type
→ Operator
→ Condition
→ Loop
→ Function
→ Array
→ String
→ Pointer
→ Struct
→ Dynamic Memory
→ File
→ Data Structure
→ Algorithm
→ Debugging
→ System Programming
```

**កុំរំលង Pointer និង Memory Management** ព្រោះវាជាចំណុចសំខាន់បំផុតមួយនៅក្នុង C។

---

## ⭐ Practice Rule

Don't only read C code.

Use this cycle:

```text
READ
 ↓
UNDERSTAND
 ↓
TYPE THE CODE
 ↓
COMPILE
 ↓
RUN
 ↓
MAKE A MISTAKE
 ↓
DEBUG
 ↓
MODIFY
 ↓
BUILD YOUR OWN PROJECT
```

> **The best way to learn C is to write C.**
>
> **វិធីល្អបំផុតក្នុងការរៀន C គឺសរសេរ C ដោយខ្លួនឯង។**
