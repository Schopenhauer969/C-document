# 📘 គម្រោង C Programming — ចាប់ពីដំបូងដល់កម្រិតខ្ពស់
> **ភាសា:** ខ្មែរ 🇰🇭 | **កម្រិត:** Beginner → Advanced  
> **គោលបំណង:** សៀវភៅណែនាំ C Programming ដ៏គ្រប់ជ្រុងជ្រោយ សម្រាប់អ្នកចាប់ផ្តើម រហូតដល់អ្នកជំនាញ

---

## 📋 តារាងមាតិកា (Table of Contents)

1. [ការណែនាំអំពីភាសា C](#1-ការណែនាំអំពីភាសា-c)
2. [ការដំឡើង Environment](#2-ការដំឡើង-environment)
3. [Hello World](#3-โปรแกรมដំបូង--hello-world)
4. [ប្រភេទទិន្នន័យ (Data Types)](#4-ប្រភេទទិន្នន័យ-data-types)
5. [អថេរ (Variables) និង ថេរ (Constants)](#5-អថេរ-variables-និង-ថេរ-constants)
6. [តម្លៃ Input / Output](#6-តម្លៃ-input--output)
7. [ប្រមាណវិធី (Operators)](#7-ប្រមាណវិធី-operators)
8. [លក្ខខណ្ឌ (Conditionals)](#8-លក្ខខណ្ឌ-conditionals)
9. [រង្វិលជុំ (Loops)](#9-រង្វិលជុំ-loops)
10. [អនុគមន៍ (Functions)](#10-អនុគមន៍-functions)
11. [អារ៉េ (Arrays)](#11-អារ៉េ-arrays)
12. [String](#12-string)
13. [Pointer](#13-pointer)
14. [Structure និង Union](#14-structure-និង-union)
15. [File I/O](#15-file-io)
16. [Dynamic Memory Allocation](#16-dynamic-memory-allocation)
17. [Preprocessor](#17-preprocessor)
18. [Error Handling](#18-error-handling)
19. [Advanced Topics](#19-advanced-topics)
20. [គន្លឹះសរសេរ Clean Code](#20-គន្លឹះសរសេរ-clean-code)

---

## 1. ការណែនាំអំពីភាសា C

### ✅ C គឺជាអ្វី?

ភាសា **C** ត្រូវបានបង្កើតឡើងដោយ **Dennis Ritchie** នៅឆ្នាំ **1972** នៅ Bell Labs។  
វាជាភាសា **low-level + high-level** ដំណាលគ្នា ហើយត្រូវបានប្រើជា base ក្នុងភាសា C++, Java, Python, និង Go។

### 🔑 លក្ខណៈពិសេស
- ⚡ **លឿន និង ប្រសិទ្ធភាពខ្ពស់** — ប្រើក្នុង OS, Embedded Systems, Game Engines
- 🔧 **Control ទាប** — គ្រប់គ្រង Memory ដោយខ្លួនឯង
- 📦 **Portable** — Code ដំណើរការបានលើ Platform ជាច្រើន
- 🧱 **Foundation** — ប្រសិនបើចេះ C ច្បាស់ ការរៀនភាសាផ្សេងក្លាយជារឿងងាយ

---

## 2. ការដំឡើង Environment

### Windows
```
1. ទាញ MinGW: https://www.mingw-w64.org/
2. ដំឡើង VS Code: https://code.visualstudio.com/
3. ដំឡើង Extension "C/C++" ក្នុង VS Code
```

### Linux / macOS
```bash
# Linux (Ubuntu/Debian)
sudo apt update
sudo apt install gcc build-essential

# macOS
xcode-select --install

# ពិនិត្យ version
gcc --version
```

### ការ Compile និង Run
```bash
# Compile
gcc hello.c -o hello

# Run
./hello
```

---

## 3. Hello World

```c
/*
 * ឯកសារ : hello.c
 * គោលបំណង : បង្ហាញ "Hello, World!" លើ Terminal
 */

#include <stdio.h>   // Library សម្រាប់ Input/Output

int main(void) {
    printf("Hello, World!\n");
    return 0;         // 0 = Program ដំណើរការជោគជ័យ
}
```

**ការបកស្រាយ:**
| ផ្នែក | មានន័យ |
|---|---|
| `#include <stdio.h>` | ដក់ចូល Library ដែល​ផ្ដល់ `printf`, `scanf` |
| `int main(void)` | ចំណុចចាប់ផ្ដើម Program |
| `printf(...)` | Print លើ Screen |
| `return 0` | ប្រាប់ OS ថា Program ជោគជ័យ |

---

## 4. ប្រភេទទិន្នន័យ (Data Types)

```c
#include <stdio.h>

int main(void) {

    /* ========== Integer Types ========== */
    int          age    = 25;           // -2,147,483,648 ដល់ 2,147,483,647
    short        s      = 100;          // -32,768 ដល់ 32,767
    long         pop    = 1000000L;     // ចំនួនធំ
    long long    big    = 9000000000LL; // ចំនួនធំណាស់
    unsigned int u_age  = 25u;          // 0 ដល់ 4,294,967,295 (គ្មានអវិជ្ជមាន)

    /* ========== Floating Point Types ========== */
    float        price  = 9.99f;        // 6-7 decimal digits
    double       pi     = 3.14159265;   // 15-16 decimal digits
    long double  ld     = 3.141592653L; // កាន់តែច្រើន digits

    /* ========== Character Type ========== */
    char         grade  = 'A';          // តួអក្សរ 1 តួ (1 byte)

    /* ========== Boolean (ត្រូវ #include <stdbool.h>) ========== */
    _Bool        is_ok  = 1;            // 1 = true, 0 = false

    printf("Age    : %d\n",   age);
    printf("Price  : %.2f\n", price);
    printf("Pi     : %.8f\n", pi);
    printf("Grade  : %c\n",   grade);

    return 0;
}
```

### ទំហំ (Size) នៃ Data Types
```c
#include <stdio.h>

int main(void) {
    printf("int       : %zu bytes\n", sizeof(int));
    printf("long      : %zu bytes\n", sizeof(long));
    printf("float     : %zu bytes\n", sizeof(float));
    printf("double    : %zu bytes\n", sizeof(double));
    printf("char      : %zu bytes\n", sizeof(char));
    return 0;
}
```

---

## 5. អថេរ (Variables) និង ថេរ (Constants)

```c
#include <stdio.h>

/* =========================================
 * CONSTANT — តម្លៃមិនអាចផ្លាស់ប្ដូរ
 * ========================================= */
#define PI        3.14159265   // Preprocessor Constant
#define MAX_SIZE  100

int main(void) {

    /* --- Variables (អថេរ) --- */
    int   score     = 0;          // ប្រកាស + Assign
    float radius;                 // ប្រកាស មុន
    radius = 5.0f;                // Assign ក្រោយ

    /* --- const keyword --- */
    const double GRAVITY = 9.81;  // មិនអាចផ្លាស់ប្ដូរ

    /* --- ការគណនា --- */
    double area = PI * radius * radius;

    printf("Radius : %.1f\n",  radius);
    printf("Area   : %.4f\n",  area);
    printf("Gravity: %.2f\n",  GRAVITY);

    /* GRAVITY = 10.0; */  // ❌ Error! const មិនអាចផ្លាស់ប្ដូរ

    return 0;
}
```

---

## 6. តម្លៃ Input / Output

```c
#include <stdio.h>

int main(void) {

    int    age;
    float  height;
    char   name[50];

    /* --- Input --- */
    printf("បញ្ចូលឈ្មោះ   : ");
    scanf("%49s", name);           // %49s — ការពារ Buffer Overflow

    printf("បញ្ចូលអាយុ   : ");
    scanf("%d", &age);             // & = address នៃ variable

    printf("បញ្ចូលកម្ពស់ : ");
    scanf("%f", &height);

    /* --- Output --- */
    printf("\n========== ព័ត៌មាន ==========\n");
    printf("ឈ្មោះ  : %s\n",   name);
    printf("អាយុ   : %d ឆ្នាំ\n", age);
    printf("កម្ពស់ : %.1f ម៉ែត្រ\n", height);

    return 0;
}
```

### Format Specifiers សំខាន់ៗ
| Specifier | ប្រភេទ | ឧទាហរណ៍ |
|---|---|---|
| `%d` | int | `printf("%d", 42)` |
| `%f` | float/double | `printf("%.2f", 3.14)` |
| `%c` | char | `printf("%c", 'A')` |
| `%s` | string | `printf("%s", "hello")` |
| `%ld` | long | `printf("%ld", 1000000L)` |
| `%lld` | long long | `printf("%lld", 9e18)` |
| `%zu` | size_t | `printf("%zu", sizeof(int))` |
| `%p` | pointer | `printf("%p", ptr)` |

---

## 7. ប្រមាណវិធី (Operators)

```c
#include <stdio.h>

int main(void) {

    int a = 10, b = 3;

    /* ========== Arithmetic ========== */
    printf("=== Arithmetic ===\n");
    printf("%d + %d = %d\n",  a, b, a + b);   // 13
    printf("%d - %d = %d\n",  a, b, a - b);   // 7
    printf("%d * %d = %d\n",  a, b, a * b);   // 30
    printf("%d / %d = %d\n",  a, b, a / b);   // 3  (Integer division)
    printf("%d %% %d = %d\n", a, b, a % b);   // 1  (Remainder)

    /* ========== Relational ========== */
    printf("\n=== Relational ===\n");
    printf("%d == %d : %d\n", a, b, a == b);  // 0 = false
    printf("%d != %d : %d\n", a, b, a != b);  // 1 = true
    printf("%d >  %d : %d\n", a, b, a >  b);  // 1 = true
    printf("%d <= %d : %d\n", a, b, a <= b);  // 0 = false

    /* ========== Logical ========== */
    printf("\n=== Logical ===\n");
    printf("(a>0 && b>0) : %d\n", (a > 0 && b > 0)); // AND — 1
    printf("(a<0 || b>0) : %d\n", (a < 0 || b > 0)); // OR  — 1
    printf("!(a == b)    : %d\n", !(a == b));         // NOT — 1

    /* ========== Assignment ========== */
    printf("\n=== Assignment ===\n");
    int x = 5;
    x += 3;  printf("x += 3 : %d\n", x);   // 8
    x -= 2;  printf("x -= 2 : %d\n", x);   // 6
    x *= 4;  printf("x *= 4 : %d\n", x);   // 24
    x /= 6;  printf("x /= 6 : %d\n", x);   // 4
    x %= 3;  printf("x %%= 3 : %d\n", x);  // 1

    /* ========== Increment / Decrement ========== */
    printf("\n=== Increment/Decrement ===\n");
    int n = 5;
    printf("n++  : %d\n", n++);  // ប្រើ n ហើយ ++ (5)
    printf("n    : %d\n", n);    // 6
    printf("++n  : %d\n", ++n);  // ++ ហើយ ប្រើ (7)

    return 0;
}
```

---

## 8. លក្ខខណ្ឌ (Conditionals)

### if / else if / else
```c
#include <stdio.h>

int main(void) {

    int score;
    printf("បញ្ចូលពិន្ទុ (0-100): ");
    scanf("%d", &score);

    if (score >= 90) {
        printf("ថ្នាក់ A — ល្អប្រសើរ! 🌟\n");
    } else if (score >= 80) {
        printf("ថ្នាក់ B — ល្អ\n");
    } else if (score >= 70) {
        printf("ថ្នាក់ C — មធ្យម\n");
    } else if (score >= 60) {
        printf("ថ្នាក់ D — ត្រូវការកែ\n");
    } else {
        printf("ថ្នាក់ F — ធ្លាក់\n");
    }

    return 0;
}
```

### switch / case
```c
#include <stdio.h>

int main(void) {

    int day;
    printf("បញ្ចូលថ្ងៃ (1-7): ");
    scanf("%d", &day);

    switch (day) {
        case 1:  printf("ថ្ងៃអាទិត្យ\n");   break;
        case 2:  printf("ថ្ងៃចន្ទ\n");       break;
        case 3:  printf("ថ្ងៃអង្គារ\n");     break;
        case 4:  printf("ថ្ងៃពុធ\n");        break;
        case 5:  printf("ថ្ងៃព្រហស្បត្តិ\n"); break;
        case 6:  printf("ថ្ងៃសុក្រ\n");      break;
        case 7:  printf("ថ្ងៃសៅរ៍\n");       break;
        default: printf("ថ្ងៃមិនត្រឹមត្រូវ\n");
    }

    return 0;
}
```

### Ternary Operator
```c
int age = 20;
// condition ? value_if_true : value_if_false
const char *status = (age >= 18) ? "ពេញវ័យ" : "អនីតិជន";
printf("%s\n", status);
```

---

## 9. រង្វិលជុំ (Loops)

### for loop
```c
#include <stdio.h>

int main(void) {

    /* --- for loop ធម្មតា --- */
    printf("=== for loop ===\n");
    for (int i = 1; i <= 5; i++) {
        printf("ជំហានទី %d\n", i);
    }

    /* --- Nested for loop (តារាងគុណ) --- */
    printf("\n=== តារាងគុណ ===\n");
    for (int i = 1; i <= 3; i++) {
        for (int j = 1; j <= 3; j++) {
            printf("%2d ", i * j);
        }
        printf("\n");
    }

    return 0;
}
```

### while loop
```c
#include <stdio.h>

int main(void) {

    int count = 1;

    printf("=== while loop ===\n");
    while (count <= 5) {
        printf("Count: %d\n", count);
        count++;
    }

    return 0;
}
```

### do-while loop
```c
#include <stdio.h>

int main(void) {

    int number;

    /* do-while ដំណើរការ 1 ដងជានិច្ច មុន check condition */
    do {
        printf("បញ្ចូលលេខវិជ្ជមាន: ");
        scanf("%d", &number);

        if (number <= 0) {
            printf("❌ លេខត្រូវតែធំជាង 0!\n");
        }
    } while (number <= 0);

    printf("✅ លេខបានទទួល: %d\n", number);

    return 0;
}
```

### break និង continue
```c
#include <stdio.h>

int main(void) {

    printf("=== break ===\n");
    for (int i = 1; i <= 10; i++) {
        if (i == 6) break;           // ឈប់ loop ភ្លាម
        printf("%d ", i);
    }
    printf("\n");  // 1 2 3 4 5

    printf("=== continue ===\n");
    for (int i = 1; i <= 10; i++) {
        if (i % 2 == 0) continue;   // រំលង លេខគូ
        printf("%d ", i);
    }
    printf("\n");  // 1 3 5 7 9

    return 0;
}
```

---

## 10. អនុគមន៍ (Functions)

```c
#include <stdio.h>

/* =========================================
 * Function Prototypes (Declaration)
 * ========================================= */
int    add(int a, int b);
double circle_area(double radius);
void   greet(const char *name);

/* =========================================
 * main
 * ========================================= */
int main(void) {

    int result = add(10, 20);
    printf("10 + 20 = %d\n", result);

    double area = circle_area(5.0);
    printf("ផ្ទៃដីរង្វង់ = %.4f\n", area);

    greet("Sophea");

    return 0;
}

/* =========================================
 * Function Definitions
 * ========================================= */

/* បន្ថែមលេខ 2 ចំនួន */
int add(int a, int b) {
    return a + b;
}

/* គណនា​ ផ្ទៃដី​រង្វង់ */
double circle_area(double radius) {
    const double PI = 3.14159265;
    return PI * radius * radius;
}

/* Print សួស្ដី — return void (គ្មាន return value) */
void greet(const char *name) {
    printf("សួស្ដី, %s! 👋\n", name);
}
```

### Recursion (ការហៅខ្លួនឯង)
```c
#include <stdio.h>

/* Factorial: n! = n * (n-1) * ... * 1 */
long long factorial(int n) {
    if (n <= 1) return 1;              // Base case
    return n * factorial(n - 1);      // Recursive call
}

/* Fibonacci */
int fibonacci(int n) {
    if (n <= 0) return 0;
    if (n == 1) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main(void) {
    printf("5! = %lld\n", factorial(5));     // 120
    printf("fib(8) = %d\n", fibonacci(8));  // 21
    return 0;
}
```

---

## 11. អារ៉េ (Arrays)

```c
#include <stdio.h>

#define N 5

int main(void) {

    /* ========== 1D Array ========== */
    int scores[N] = {85, 92, 78, 95, 88};

    int sum = 0;
    for (int i = 0; i < N; i++) {
        sum += scores[i];
        printf("scores[%d] = %d\n", i, scores[i]);
    }
    printf("ពិន្ទុសរុប   : %d\n", sum);
    printf("ពិន្ទុជាមធ្យម : %.1f\n", (double)sum / N);

    /* ========== 2D Array (Matrix) ========== */
    printf("\n=== Matrix 3x3 ===\n");
    int matrix[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    for (int row = 0; row < 3; row++) {
        for (int col = 0; col < 3; col++) {
            printf("%3d", matrix[row][col]);
        }
        printf("\n");
    }

    return 0;
}
```

---

## 12. String

```c
#include <stdio.h>
#include <string.h>   // Library សម្រាប់ String functions

int main(void) {

    char name1[50] = "Sophea";
    char name2[50] = "Dara";
    char full[100];

    /* strlen — ប្រវែង String */
    printf("ប្រវែង name1 : %zu\n", strlen(name1));   // 6

    /* strcpy — ចម្លង String */
    char copy[50];
    strcpy(copy, name1);
    printf("Copy : %s\n", copy);

    /* strcat — ភ្ជាប់ String */
    strcpy(full, name1);
    strcat(full, " & ");
    strcat(full, name2);
    printf("Full : %s\n", full);    // "Sophea & Dara"

    /* strcmp — ប្រៀបធៀប String */
    int cmp = strcmp(name1, name2);
    if (cmp == 0)       printf("ដូចគ្នា\n");
    else if (cmp < 0)   printf("name1 < name2\n");
    else                printf("name1 > name2\n");

    /* ======================================
     * String ជា Array នៃ char
     * ====================================== */
    char word[] = "Hello";
    printf("\nChar by char: ");
    for (int i = 0; word[i] != '\0'; i++) {   // '\0' = End of String
        printf("%c", word[i]);
    }
    printf("\n");

    return 0;
}
```

---

## 13. Pointer

> **Pointer** គឺជា variable ដែលរក្សា **address** (អាស័យដ្ឋាន) នៃ variable មួយផ្សេងទៀត

```c
#include <stdio.h>

int main(void) {

    int num  = 42;
    int *ptr = &num;       // ptr ទុក address របស់ num

    printf("=== Pointer Basics ===\n");
    printf("num       = %d\n",   num);      // តម្លៃ: 42
    printf("&num      = %p\n",   &num);     // address
    printf("ptr       = %p\n",   ptr);      // address (ដូច &num)
    printf("*ptr      = %d\n",   *ptr);     // Dereference: 42

    /* ផ្លាស់ប្ដូរ num តាមរយៈ pointer */
    *ptr = 100;
    printf("\nAfter *ptr = 100:\n");
    printf("num = %d\n", num);              // 100

    /* ======================================
     * Pointer & Arrays
     * ====================================== */
    printf("\n=== Pointer + Array ===\n");
    int arr[] = {10, 20, 30, 40, 50};
    int *p    = arr;                        // arr = &arr[0]

    for (int i = 0; i < 5; i++) {
        printf("arr[%d] = %d  (via pointer: %d)\n",
               i, arr[i], *(p + i));
    }

    /* ======================================
     * Pointer ក្នុង Function (Pass by Reference)
     * ====================================== */
    return 0;
}

/* Swap ដោយប្រើ Pointer */
void swap(int *a, int *b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}
```

---

## 14. Structure និង Union

```c
#include <stdio.h>
#include <string.h>

/* =======================================
 * struct — ក្រុម Data Types ផ្សេងៗគ្នា
 * ======================================= */
typedef struct {
    char  name[50];
    int   age;
    float gpa;
} Student;

/* Nested struct */
typedef struct {
    int day;
    int month;
    int year;
} Date;

typedef struct {
    char name[50];
    Date birthday;
    float salary;
} Employee;

/* ======================================= */

void print_student(const Student *s) {
    printf("ឈ្មោះ  : %s\n",   s->name);
    printf("អាយុ   : %d\n",   s->age);
    printf("GPA    : %.2f\n", s->gpa);
}

int main(void) {

    /* --- ប្រើ struct --- */
    Student s1;
    strcpy(s1.name, "Sreyleak");
    s1.age = 20;
    s1.gpa = 3.85f;

    Student s2 = {"Visal", 22, 3.60f};   // Initialize ផ្ទាល់

    printf("=== Student 1 ===\n");
    print_student(&s1);

    printf("\n=== Student 2 ===\n");
    print_student(&s2);

    /* --- Array of Structs --- */
    printf("\n=== Class List ===\n");
    Student class[3] = {
        {"Arun",    21, 3.75f},
        {"Bopha",   20, 3.90f},
        {"Chamroen",22, 3.55f}
    };

    for (int i = 0; i < 3; i++) {
        printf("%d. %-12s GPA: %.2f\n",
               i + 1, class[i].name, class[i].gpa);
    }

    return 0;
}
```

---

## 15. File I/O

```c
#include <stdio.h>
#include <stdlib.h>  // exit()

/* ======================================
 * សរសេរ (Write) ទៅ File
 * ====================================== */
void write_file(void) {
    FILE *fp = fopen("students.txt", "w");   // "w" = write mode
    if (fp == NULL) {
        perror("Error opening file");
        exit(EXIT_FAILURE);
    }

    fprintf(fp, "Sophea  20  3.85\n");
    fprintf(fp, "Dara    22  3.70\n");
    fprintf(fp, "Sreyleak 21 3.90\n");

    fclose(fp);
    printf("✅ សរសេរ File ជោគជ័យ!\n");
}

/* ======================================
 * អាន (Read) ពី File
 * ====================================== */
void read_file(void) {
    FILE *fp = fopen("students.txt", "r");   // "r" = read mode
    if (fp == NULL) {
        perror("Error opening file");
        exit(EXIT_FAILURE);
    }

    char   name[50];
    int    age;
    double gpa;

    printf("\n=== File Content ===\n");
    while (fscanf(fp, "%s %d %lf", name, &age, &gpa) == 3) {
        printf("ឈ្មោះ: %-10s | អាយុ: %d | GPA: %.2f\n",
               name, age, gpa);
    }

    fclose(fp);
}

int main(void) {
    write_file();
    read_file();
    return 0;
}
```

### File Modes
| Mode | មានន័យ |
|---|---|
| `"r"` | Read — file ត្រូវតែមានស្រាប់ |
| `"w"` | Write — បង្កើត/ជម្នះ file ចាស់ |
| `"a"` | Append — បន្ថែមទៅចុង file |
| `"r+"` | Read + Write |
| `"rb"` | Read binary |
| `"wb"` | Write binary |

---

## 16. Dynamic Memory Allocation

```c
#include <stdio.h>
#include <stdlib.h>  // malloc, calloc, realloc, free

int main(void) {

    int n;
    printf("បញ្ចូលចំនួន elements: ");
    scanf("%d", &n);

    /* ======================================
     * malloc — Allocate memory (uninitialized)
     * ====================================== */
    int *arr = (int *)malloc(n * sizeof(int));
    if (arr == NULL) {
        fprintf(stderr, "❌ Memory allocation failed!\n");
        return EXIT_FAILURE;
    }

    /* បំពេញ values */
    for (int i = 0; i < n; i++) {
        arr[i] = (i + 1) * 10;
    }

    printf("malloc array: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", arr[i]);
    }
    printf("\n");

    /* ======================================
     * realloc — ពង្រីក/បង្រួម Memory
     * ====================================== */
    int new_size = n + 3;
    int *tmp = (int *)realloc(arr, new_size * sizeof(int));
    if (tmp == NULL) {
        free(arr);   // ត្រូវ free arr ដ៏ "ដើម
        return EXIT_FAILURE;
    }
    arr = tmp;

    /* ======================================
     * calloc — Allocate + Initialize to 0
     * ====================================== */
    double *matrix = (double *)calloc(4 * 4, sizeof(double));
    if (matrix != NULL) {
        printf("calloc 4x4 matrix (all zeros initialized)\n");
        free(matrix);
    }

    /* ======================================
     * IMPORTANT: free() ដើម្បីជៀសវាង Memory Leak
     * ====================================== */
    free(arr);    // ❗ ត្រូវ free រាល់ malloc/calloc/realloc

    return 0;
}
```

---

## 17. Preprocessor

```c
#include <stdio.h>

/* ======================================
 * #define Macros
 * ====================================== */
#define MAX(a, b)       ((a) > (b) ? (a) : (b))
#define MIN(a, b)       ((a) < (b) ? (a) : (b))
#define SQUARE(x)       ((x) * (x))
#define ABS(x)          ((x) < 0 ? -(x) : (x))

/* ======================================
 * Conditional Compilation
 * ====================================== */
#define DEBUG_MODE   1

#if DEBUG_MODE
    #define LOG(msg)  printf("[DEBUG] %s\n", (msg))
#else
    #define LOG(msg)  /* nothing */
#endif

int main(void) {

    printf("MAX(10, 20)   = %d\n", MAX(10, 20));
    printf("MIN(10, 20)   = %d\n", MIN(10, 20));
    printf("SQUARE(7)     = %d\n", SQUARE(7));
    printf("ABS(-42)      = %d\n", ABS(-42));

    LOG("Program started");

    return 0;
}
```

---

## 18. Error Handling

```c
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>   // errno
#include <string.h>  // strerror

int divide(int a, int b, int *result) {
    if (b == 0) {
        return -1;   // Error code
    }
    *result = a / b;
    return 0;        // Success
}

int main(void) {

    int result;

    /* --- Custom Error Code --- */
    if (divide(10, 0, &result) != 0) {
        fprintf(stderr, "❌ Error: Cannot divide by zero!\n");
    } else {
        printf("10 / 2 = %d\n", result);
    }

    if (divide(10, 2, &result) == 0) {
        printf("10 / 2 = %d\n", result);
    }

    /* --- errno (System Error) --- */
    FILE *fp = fopen("nonexistent_file.txt", "r");
    if (fp == NULL) {
        printf("errno = %d\n",    errno);
        printf("Error : %s\n",    strerror(errno));
        perror("fopen failed");   // Print error message
    }

    return 0;
}
```

---

## 19. Advanced Topics

### Function Pointers
```c
#include <stdio.h>

int  add(int a, int b)  { return a + b; }
int  sub(int a, int b)  { return a - b; }
int  mul(int a, int b)  { return a * b; }

/* Function pointer type */
typedef int (*Operation)(int, int);

void apply(int a, int b, Operation op, const char *name) {
    printf("%s(%d, %d) = %d\n", name, a, b, op(a, b));
}

int main(void) {
    apply(10, 5, add, "add");
    apply(10, 5, sub, "sub");
    apply(10, 5, mul, "mul");

    /* Array of function pointers */
    Operation ops[]       = {add, sub, mul};
    const char *names[]   = {"add", "sub", "mul"};

    for (int i = 0; i < 3; i++) {
        apply(8, 4, ops[i], names[i]);
    }

    return 0;
}
```

### Linked List
```c
#include <stdio.h>
#include <stdlib.h>

/* =======================================
 * Node Structure
 * ======================================= */
typedef struct Node {
    int          data;
    struct Node *next;
} Node;

/* =======================================
 * Operations
 * ======================================= */

/* បន្ថែម node នៅខាងចុង */
Node *push_back(Node *head, int value) {
    Node *new_node = (Node *)malloc(sizeof(Node));
    if (new_node == NULL) return head;

    new_node->data = value;
    new_node->next = NULL;

    if (head == NULL) return new_node;

    Node *cur = head;
    while (cur->next != NULL) cur = cur->next;
    cur->next = new_node;

    return head;
}

/* Print Linked List */
void print_list(const Node *head) {
    printf("List: ");
    for (const Node *cur = head; cur != NULL; cur = cur->next) {
        printf("%d", cur->data);
        if (cur->next) printf(" -> ");
    }
    printf(" -> NULL\n");
}

/* Free memory */
void free_list(Node *head) {
    while (head != NULL) {
        Node *tmp = head;
        head = head->next;
        free(tmp);
    }
}

int main(void) {
    Node *list = NULL;

    for (int i = 1; i <= 5; i++) {
        list = push_back(list, i * 10);
    }

    print_list(list);   // List: 10 -> 20 -> 30 -> 40 -> 50 -> NULL
    free_list(list);

    return 0;
}
```

---

## 20. គន្លឹះសរសេរ Clean Code

### ✅ បទដ្ឋានល្អ
```c
/* ❌ BAD — ពិបាកអាន */
int f(int x,int y){int z=x+y;return z;}

/* ✅ GOOD — ច្បាស់លាស់ */
/**
 * @brief  គណនាផលបូកនៃ a និង b
 * @param  a  ចំនួនទីមួយ
 * @param  b  ចំនួនទីពីរ
 * @return ផលបូក a + b
 */
int calculate_sum(int a, int b) {
    return a + b;
}
```

### 📐 ច្បាប់ Clean Code ក្នុង C

| ក្បួន | ការអនុវត្ត |
|---|---|
| **ឈ្មោះ Variable** | ប្រើ `snake_case`: `total_score`, `student_name` |
| **ឈ្មោះ Function** | ប្រើ Verb: `calculate_area()`, `read_file()` |
| **ឈ្មោះ Constants** | ប្រើ UPPERCASE: `MAX_SIZE`, `PI` |
| **Comment** | ពន្យល់ *ហេតុអ្វី* មិនមែន *ធ្វើអ្វី* |
| **Function** | Function 1 ទំព័រ — 20-30 lines max |
| **Magic Numbers** | ជៀសវាង `if (n > 100)` → ប្រើ `#define MAX_LIMIT 100` |
| **Error Check** | Check return value រាល់ malloc, fopen |
| **Memory** | Free every malloc — ប្រើ Valgrind ពិនិត្យ |

### 🧪 Good Code Example
```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_STUDENTS  100
#define NAME_LEN       50

typedef struct {
    char  name[NAME_LEN];
    float gpa;
} Student;

/* ចម្រោះ Students ដែលមាន GPA >= min_gpa */
int filter_students(
    const Student *src,
    int            src_count,
    Student       *dst,
    float          min_gpa
) {
    int count = 0;
    for (int i = 0; i < src_count; i++) {
        if (src[i].gpa >= min_gpa) {
            dst[count++] = src[i];
        }
    }
    return count;
}

int main(void) {
    Student students[] = {
        {"Sophea",   3.85f},
        {"Dara",     2.90f},
        {"Sreyleak", 3.70f},
        {"Visal",    3.20f},
        {"Bopha",    3.95f},
    };
    int total = 5;

    Student honor[MAX_STUDENTS];
    int honor_count = filter_students(students, total, honor, 3.50f);

    printf("=== Honor Students (GPA >= 3.50) ===\n");
    for (int i = 0; i < honor_count; i++) {
        printf("%-12s : %.2f\n", honor[i].name, honor[i].gpa);
    }

    return 0;
}
```

---

## 📚 Resources ផ្សេងៗ

| ប្រភព | Link |
|---|---|
| C Reference | https://en.cppreference.com/w/c |
| The C Programming Language (Book) | K&R Classic Book |
| CS50 Harvard | https://cs50.harvard.edu |
| GCC Docs | https://gcc.gnu.org/onlinedocs/ |
| Valgrind (Memory Checker) | https://valgrind.org |

---

## 🗺️ ផ្លូវវិភាគ (Learning Roadmap)

```
ដំណាក់កាលទី 1 (Beginner)
├── Variables & Data Types
├── Input / Output
├── Operators
├── Conditionals
└── Loops

ដំណាក់កាលទី 2 (Intermediate)
├── Functions
├── Arrays & Strings
├── Pointers (Basic)
└── Structs

ដំណាក់កាលទី 3 (Advanced)
├── Pointers (Advanced)
├── Dynamic Memory
├── File I/O
├── Data Structures (List, Stack, Queue)
└── Algorithms (Sort, Search)

ដំណាក់កាលទី 4 (Expert)
├── Bitwise Operations
├── Multi-file Projects
├── Makefiles
└── System Programming (Linux, OS, Sockets)
```

---

> ✍️ **ត្រូវចាំ:** "Programs must be written for people to read, and only incidentally for machines to execute." — Harold Abelson


