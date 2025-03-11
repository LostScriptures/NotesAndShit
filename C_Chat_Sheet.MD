# C Cheat Sheet

## 1. Basic Structure
```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

## 2. Data Types
- `int` - Integer
- `float` - Floating point number
- `double` - Double precision float
- `char` - Character
- `void` - No value

## 3. Operators
- Arithmetic: `+`, `-`, `*`, `/`, `%`
- Relational: `==`, `!=`, `<`, `>`, `<=`, `>=`
- Logical: `&&`, `||`, `!`
- Bitwise: `&`, `|`, `^`, `~`, `<<`, `>>`
- Assignment: `=`, `+=`, `-=`, `*=`, `/=`, `%=`
- Increment/Decrement: `++`, `--`

## 4. Control Flow
### If-Else
```c
if (condition) {
    // code
} else if (condition) {
    // code
} else {
    // code
}
```
### Switch Case
```c
switch (variable) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // code
}
```
### Loops
#### For Loop
```c
for (initialization; condition; update) {
    // code
}
```
#### While Loop
```c
while (condition) {
    // code
}
```
#### Do-While Loop
```c
do {
    // code
} while (condition);
```

## 5. Functions
```c
return_type function_name(parameters) {
    // code
    return value;
}
```
Example:
```c
int add(int a, int b) {
    return a + b;
}
```

## 6. Arrays
```c
type array_name[size];
int arr[5] = {1, 2, 3, 4, 5};
```

## 7. Strings
```c
char str[] = "Hello";
char str2[10];
scanf("%s", str2);
printf("%s", str);
```

## 8. Pointers
```c
int *ptr;
int a = 10;
ptr = &a;
printf("%d", *ptr);  // Dereferencing
```

## 9. Structures
```c
struct Person {
    char name[50];
    int age;
};
```

## 10. File Handling
```c
FILE *fp;
fp = fopen("file.txt", "w");
fprintf(fp, "Hello, File!");
fclose(fp);
```

## 11. Memory Allocation
```c
int *ptr = (int*)malloc(sizeof(int));
free(ptr);
```

## 12. Standard Library Functions
### Input/Output (`#include <stdio.h>`)
```c
printf("Format Specifiers: %d %f %c", int_var, float_var, char_var); // Prints formatted output to the console.
scanf("%d", &var); // Reads formatted input from the user.
gets(str); // Reads a line of text (deprecated, use fgets instead).
fgets(str, size, stdin); // Reads a line of text with size limit.
putchar(ch); // Prints a single character to the console.
puts(str); // Prints a string followed by a newline.
```
### String Handling (`#include <string.h>`)
```c
strcpy(dest, src); // Copies src string to dest.
strcat(dest, src); // Appends src to dest.
strlen(str); // Returns the length of the string.
strcmp(str1, str2); // Compares two strings.
strchr(str, ch); // Finds first occurrence of character ch in str.
strstr(str1, str2); // Finds first occurrence of str2 in str1.
```
### Math (`#include <math.h>`)
```c
pow(x, y); // Computes x raised to the power y.
sqrt(x); // Computes square root of x.
fabs(x); // Returns absolute value of x.
ceil(x); // Rounds x up to the nearest integer.
floor(x); // Rounds x down to the nearest integer.
```
### Time (`#include <time.h>`)
```c
time_t t;
time(&t); // Gets current system time.
printf("%s", ctime(&t)); // Converts time to string format.
clock_t start = clock(); // Returns processor time consumed by program.
```
### Utility (`#include <stdlib.h>`)
```c
atoi(str); // Converts string to integer.
rand(); // Generates a random number.
srand(time(0)); // Seeds random number generator.
exit(0); // Exits the program.
```

## 13. Example Exercises
### 1. Sum of Two Numbers
```c
#include <stdio.h>

int main() {
    int a, b, sum;
    printf("Enter two numbers: ");
    scanf("%d %d", &a, &b);
    sum = a + b;
    printf("Sum: %d\n", sum);
    return 0;
}
```
### 2. Factorial of a Number
```c
#include <stdio.h>

int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n - 1);
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    printf("Factorial: %d\n", factorial(num));
    return 0;
}
```
### 3. Reverse a String
```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[100], rev[100];
    printf("Enter a string: ");
    scanf("%s", str);
    int len = strlen(str);
    for (int i = 0; i < len; i++) {
        rev[i] = str[len - i - 1];
    }
    rev[len] = '\0';
    printf("Reversed: %s\n", rev);
    return 0;
}
```
### 4. Check if a Number is Prime
```c
#include <stdio.h>

int is_prime(int num) {
    if (num <= 1) return 0;
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) return 0;
    }
    return 1;
}

int main() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    if (is_prime(num))
        printf("%d is prime\n", num);
    else
        printf("%d is not prime\n", num);
    return 0;
}
```
### 5. Fibonacci Series using Recursion
```c
#include <stdio.h>

int fibonacci(int n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    int n;
    printf("Enter the number of terms: ");
    scanf("%d", &n);
    printf("Fibonacci Series: ");
    for (int i = 0; i < n; i++) {
        printf("%d ", fibonacci(i));
    }
    printf("\n");
    return 0;
}
```

This cheat sheet covers the fundamental concepts of C programming concisely!

