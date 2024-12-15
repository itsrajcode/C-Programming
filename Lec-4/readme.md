# Data Types in C Programming

## Integer Data Type
The **integer data type** in C is used to store whole numbers, including positive, negative, and zero, without any decimal part. It can store decimal values, octal values, and hexadecimal values.

### Properties:
- **Range:** -2,147,483,648 to 2,147,483,647
- **Size:** 4 bytes
- **Format Specifier:** `%d`

### Syntax:
To declare an integer variable, use the `int` keyword:
```c
int var_name;
```

### Variants of Integer Data Type:
- **unsigned int:** Stores only positive values (0 and above). Cannot store negative values.
- **short int:** Smaller size (2 bytes); range: -32,768 to 32,767.
- **long int:** Larger size; can store values greater than the `int` range.
- **unsigned short int:** Stores only positive values; similar to the relationship between `short int` and `unsigned int`.

**Note:** The size of an integer data type is compiler-dependent. Use the `sizeof` operator to check the actual size.

### Example:
```c
#include <stdio.h>

int main() {
    int a = 9;  // Positive integer
    int b = -9; // Negative integer
    unsigned int c = 89U;  // Unsigned integer
    long int d = 99998L;   // Long integer

    printf("Integer value with positive data: %d\n", a);
    printf("Integer value with negative data: %d\n", b);
    printf("Unsigned int data: %u\n", c);
    printf("Long int data: %ld\n", d);

    return 0;
}
```
**Output:**
```
Integer value with positive data: 9
Integer value with negative data: -9
Unsigned int data: 89
Long int data: 99998
```

---

## Character Data Type
The **character data type** is used to store a single character. It requires 1 byte of memory and stores the character as its ASCII value.

### Properties:
- **Range:** -128 to 127 (signed) or 0 to 255 (unsigned)
- **Size:** 1 byte
- **Format Specifier:** `%c`

### Syntax:
To declare a character variable, use the `char` keyword:
```c
char var_name;
```

### Example:
```c
#include <stdio.h>

int main() {
    char a = 'a';
    char c;

    printf("Value of a: %c\n", a);
    a++;
    printf("Value of a after increment is: %c\n", a);

    c = 99; // ASCII value for 'c'
    printf("Value of c: %c\n", c);

    return 0;
}
```
**Output:**
```
Value of a: a
Value of a after increment is: b
Value of c: c
```

---

## Float Data Type
The **float data type** is used to store decimal numbers with single precision.

### Properties:
- **Range:** 1.2E-38 to 3.4E+38
- **Size:** 4 bytes
- **Format Specifier:** `%f`

### Syntax:
To declare a floating-point variable, use the `float` keyword:
```c
float var_name;
```

### Example:
```c
#include <stdio.h>

int main() {
    float a = 9.0f;
    float b = 2.5f;
    float c = 2E-4f; // Scientific notation

    printf("%f\n", a);
    printf("%f\n", b);
    printf("%f\n", c);

    return 0;
}
```
**Output:**
```
9.000000
2.500000
0.000200
```

---

## Double Data Type
The **double data type** is used to store decimal numbers with double precision.

### Properties:
- **Range:** 1.7E-308 to 1.7E+308
- **Size:** 8 bytes
- **Format Specifier:** `%lf`

### Syntax:
To declare a double variable, use the `double` keyword:
```c
double var_name;
```

### Example:
```c
#include <stdio.h>

int main() {
    double a = 123123123.00;
    double b = 12.293123;
    double c = 2312312312.123123;

    printf("%lf\n", a);
    printf("%lf\n", b);
    printf("%lf\n", c);

    return 0;
}
```
**Output:**
```
123123123.000000
12.293123
2312312312.123123
```

---

## Void Data Type
The **void data type** is used to represent the absence of any value. It is commonly used:
- As a return type for functions that do not return any value.
- For functions that do not take any parameters.
- With pointers to represent a generic pointer.

### Syntax:
```c
// Function return type void
void exit(int check);

// Function without any parameters
int print(void);

// Generic pointer
void *malloc(size_t size);
```

### Example:
```c
#include <stdio.h>

int main() {
    int val = 30;
    void* ptr = &val;

    printf("%d", *(int*)ptr); // Dereferencing void pointer
    return 0;
}
```
**Output:**
```
30
```

---

## Size of Data Types in C
The size of data types is architecture-dependent. Use the `sizeof` operator to determine the size of any data type.

### Example:
```c
#include <stdio.h>

int main() {
    printf("The size of int data type: %d bytes\n", sizeof(int));
    printf("The size of char data type: %d bytes\n", sizeof(char));
    printf("The size of float data type: %d bytes\n", sizeof(float));
    printf("The size of double data type: %d bytes\n", sizeof(double));

    return 0;
}
```
**Output:**
```
The size of int data type: 4 bytes
The size of char data type: 1 byte
The size of float data type: 4 bytes
The size of double data type: 8 bytes
```

---

## Summary of Data Types
| Data Type                | Size (bytes) | Range                                      | Format Specifier |
|--------------------------|--------------|--------------------------------------------|------------------|
| `short int`              | 2            | -32,768 to 32,767                          | `%hd`            |
| `unsigned short int`     | 2            | 0 to 65,535                                | `%hu`            |
| `unsigned int`           | 4            | 0 to 4,294,967,295                         | `%u`             |
| `int`                    | 4            | -2,147,483,648 to 2,147,483,647            | `%d`             |
| `long int`               | 4            | -2,147,483,648 to 2,147,483,647            | `%ld`            |
| `unsigned long int`      | 4            | 0 to 4,294,967,295                         | `%lu`            |
| `long long int`          | 8            | -(2^63) to (2^63)-1                        | `%lld`           |
| `unsigned long long int` | 8            | 0 to 18,446,744,073,709,551,615            | `%llu`           |
| `signed char`            | 1            | -128 to 127                                | `%c`             |
| `unsigned char`          | 1            | 0 to 255                                   | `%c`             |
| `float`                  | 4            | 1.2E-38 to 3.4E+38                         | `%f`             |
| `double`                 | 8            | 1.7E-308 to 1.7E+308                       | `%lf`            |
| `long double`            | 16           | 3.4E-4932 to 1.1E+4932                     | `%Lf`            |

**Note:** The `long`, `short`, `signed`, and `unsigned` are modifiers that adjust the size and range of the data types.

