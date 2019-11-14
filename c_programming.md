
# C Programming

* Compiler version
    > MSVC / GCC
* Language standard
    > C++17 / GNU11

    For Visual Studio 2019, the version information is given in

    ```text
    Project\Properties\Configuration Properties\C/C++\Language\
    *C++ Language Standard
    ```

# C Programming Basics

## Declaration / Definition

* [*cprogramming](https://www.cprogramming.com/declare_vs_define.html) [*geeksforgeeks](https://www.geeksforgeeks.org/difference-between-definition-and-declaration/)
* _Declaration_ can be understood as a subset of _definition_.
* `int x;` declares `x`. It also defines `x` because a storage is allocated to the variable to store a value `0`. (`int x;` includes `x = 0;`.)
* To only declare a variable without defining, use `extern` keyword. [*geeksforgeeks](https://www.geeksforgeeks.org/understanding-extern-keyword-in-c/)

    ```c
    extern int x;
    ```

* For functions, `int fcn();` only declares the function `fcn`. Function declarations are typically organized in a header file.
* The following declares and defines the function `fcn`.

    ```c
    int fcn() {
    }
    ```

* A variable or function can be declared multiple times but it can be defined only once. The following throws an error: _'x': redefinition; multiple initialization_.

    ```c
    int x = 1;
    int x = 1;
    ```

    `int x;` shares properties of declaration and definition. But it is not equivalent to `int x = 0;` because `int x;` can be written multiple times in a program. That is,

    ```c
    int x;
    int x;
    ```

    is allowed.

## Preprocessor

* [*cprogramming](https://www.cprogramming.com/tutorial/cpreprocessor.html)

## Keywords

* [*programiz](https://www.programiz.com/c-programming/c-keywords-identifier)
* Keywords are predefined, reserved words used in programming that have special meanings to the compiler. Keywords are part of the syntax and they cannot be used as an identifier.
* List of keywords [*programiz](https://www.programiz.com/c-programming/list-all-keywords-c-language)

    ```text
    auto double int struct break else long switch case enum register typedef char extern return union continue for signed void do if static while default goto sizeof volatile const float short unsigned
    ```

## Identifiers

* [*programiz](https://www.programiz.com/c-programming/c-keywords-identifier)
* Identifier refers to name given to entities such as variables, functions, structures etc. Identifiers must be unique. They are created to give a unique name to an entity to identify it during the execution of the program. For instance, in `int n;`, `n` is an identifier.
* Identifier names must be different from keywords. `int` cannot be used as an identifier because it is a keyword.
* Rules:
  * The first letter of an identifier should be either a letter or an underscore.
  * The identifier must not exceed 31 characters, or it may cause problems in some compilers.

## Variables

* [*programiz](https://www.programiz.com/c-programming/c-variables-constants)
* A variable is a container (storage area) to hold data.

## Literals

* [*programiz](https://www.programiz.com/c-programming/c-variables-constants)
* A literal is a value (or an identifier) whose value cannot be altered in a program. For example, `1`, `2.5`, `'c'`.
* **Integer** literals

    ```text
    Decimal (base 10): 0, -9, 22 etc
    Octal (base 8): 021, 077, 033 etc
    Hexadecimal (base 16): 0x7f, 0x2a, 0x521 etc
    ```

* **Floating-point** literals

    ```c
    -2.0
    0.0000234
    -0.22E-5
    ```

* A **character** literal is created by enclosing a _single_ character inside _single_ quotation marks. For example, `'a'`, `'m'`, `'F'`, `'2'`, `'}'`.

* Escape sequences
    | Escape Sequences | Character             |
    | ---------------- | --------------------- |
    | `\b`             | Backspace             |
    | `\f`             | Form feed             |
    | `\n`             | Newline               |
    | `\r`             | Return                |
    | `\t`             | Horizontal tab        |
    | `\v`             | Vertical tab          |
    | `\\`             | Backslash             |
    | `\'`             | Single quotation mark |
    | `\"`             | Double quotation mark |
    | `\?`             | Question mark         |
    | `\0`             | Null character        |

* A **string** literal is a _sequence_ of characters enclosed in _double_-quote marks.

    ```c
    "good"                //string constant
    ""                    //null string constant
    "      "              //string constant of six white space
    "x"                   //string constant having a single character.
    "Earth is round\n"    //prints string with a newline
    ```

## Constants

* The keyword `const` is used to make the value immutable.

    ```c
    const double PI = 3.14159;
    ```

* A constant can be defined by the `#define` _preprocessor_ directive.

## Data types

* [*programiz](https://www.programiz.com/c-programming/c-data-types) [*geeksforgeeks](https://www.geeksforgeeks.org/data-types-in-c/)
* The typical size and string specifier of each type on **32 bit gcc compiler** [*geeksforgeeks](https://www.geeksforgeeks.org/data-types-in-c/)

    | Type                     | Size (bytes) | Format Specifier |
    | ------------------------ | ------------ | ---------------- |
    | `char`                   | 1            | `%c`             |
    | `int`                    | 4            | `%d`             |
    | `float`                  | 4            | `%f`             |
    | `double`                 | 8            | `%lf`            |
    | `short int`              | 2            | `%hd`            |
    | `unsigned int`           | 4            | `%u`             |
    | `long int`               | 4            | `%ld`            |
    | `long long int`          | 8            | `%lld`           |
    | `unsigned long int`      | 4            | `%lu`            |
    | `unsigned long long int` | 8            | `%llu`           |
    | `signed char`            | 1            | `%c`             |
    | `unsigned char`          | 1            | `%c`             |
    | `long double`            | 12           | `%Lf`            |

    > In 32-bit and 64-bit operating systems, the Microsoft C compiler maps long double to type double. Therefore, `sizeof(long double)` yields 8 bytes in _MSVC_. [*microsoft](https://docs.microsoft.com/en-us/cpp/c-language/data-type-specifiers-and-equivalents?view=vs-2019)
* Variables can be declared at once.

    ```c
    int x1, x2;
    ```

* The size of `int` is 4 bytes (32 bits). It can take $2^{32}$ distinct states from `-2^31 (= -2147483648)` to `2^31-1 (= 2147483647)`.
* `float` and `double` are used to hold real numbers. The size of `float` (single precision float data type) is 4 bytes. And the size of `double` (double precision float data type) is 8 bytes.
* Keyword `char` is used for declaring character type variables.

    ```c
    char s = 'a';
    ```

    The size of `char` is 1 byte.
* `void` is an incomplete type. It means "nothing" or "no type". A variable can have `void` type. Only functions that return nothing can have `void` as its return type.
* `short` and `long` are equivalent to `short int` and `long int`, respectively.
* `signed` and `unsigned` are _type modifiers_ that can change the data storage.

    ```c
    unsigned int x;
    ```

    The sizes of `int` and `unsigned int` are both 4 bytes but the values of `unsigned int` range from `0` to `2^31-1`.

## `sizeof`

* `sizeof` operator can be used to check the size of a variable in _byte_.

## Character

* Printing a character with the `%s` format specifier gives a wrong result. Use `%c` to print a single character.

    ```c
    char chr = 'a';
    printf("%c\n", chr); // proper
    printf("%s\n", chr); // wrong
    ```

## `scanf`

* Template

    ```c
    double value1;
    int value2;
    scanf_s("%lf%d", &value1, &value2);
    printf("%lf, %d\n", value1, value2);
    ```

    Use `scanf_s` in MSVC.

* Reading a string with scanf [*stackoverflow](https://stackoverflow.com/questions/5406935/reading-a-string-with-scanf).

## Operators

* Arithmetic operators
    | Operator | Meaning of Operator                        |
    | -------- | ------------------------------------------ |
    | `+`      | addition or unary plus                     |
    | `-`      | subtraction or unary minus                 |
    | `*`      | multiplication                             |
    | `/`      | division                                   |
    | `%`      | remainder after division (modulo division) |

* Increment and decrement operators\
    C programming has two operators increment `++` and decrement `--` to change the value of an operand (constant or variable) by `1`.

* Assignment operators\
    An assignment operator is used for assigning a value to a variable. The most common assignment operator is `=`.

    | Operator | Example  | Same as   |
    | -------- | -------- | --------- |
    | `=`      | `a = b`  | `a = b`   |
    | `+=`     | `a += b` | `a = a+b` |
    | `-=`     | `a -= b` | `a = a-b` |
    | `*=`     | `a *= b` | `a = a*b` |
    | `/=`     | `a /= b` | `a = a/b` |
    | `%=`     | `a %= b` | `a = a%b` |

* Relation operators\
    A relational operator checks the relationship between two operands. If the relation is true, it returns `1`; if the relation is false, it returns value `0`.

    | Operator | Meaning of Operator      | Example                      |
    | -------- | ------------------------ | ---------------------------- |
    | `==`     | Equal to                 | `5 == 3` is evaluated to `0` |
    | `>`      | Greater than             | `5 > 3` is evaluated to `1`  |
    | `<`      | Less than                | `5 < 3` is evaluated to `0`  |
    | `!=`     | Not equal to             | `5 != 3` is evaluated to `1` |
    | `>=`     | Greater than or equal to | `5 >= 3` is evaluated to `1` |
    | `<=`     | Less than or equal to    | `5 <= 3` is evaluated to `0` |

* Logical operators

    | Operator | Meaning                                             | Example                                                                    |
    | -------- | --------------------------------------------------- | -------------------------------------------------------------------------- |
    | `&&`     | Logical AND. True only if all operands are true     | If `c = 5` and `d = 2` then, expression `((c==5) && (d>5))` equals to `0`. |
    | `||`     | Logical OR. True only if either one operand is true | If `c = 5` and `d = 2` then, expression `((c==5)||(d>5))` equals to `1`.   |
    | `!`      | Logical NOT. True only if the operand is 0          | If `c = 5` then, expression `!(c==5)` equals to `0`.                       |

* Bitwise Operators\
    During computation, mathematical operations like: addition, subtraction, multiplication, division, etc are converted to bit-level which makes processing faster and saves power.

    | Operators | Meaning of operators |
    | --------- | -------------------- |
    | `&`       | Bitwise AND          |
    | `|`       | Bitwise OR           |
    | `^`       | Bitwise exclusive OR |
    | `~`       | Bitwise complement   |
    | `<<`      | Shift left           |
    | `>>`      | Shift right          |

## Increment and decrement operators

* [*wikipedia](https://en.wikipedia.org/wiki/Increment_and_decrement_operators)
* `i++` and `++i` are different operations.\
    In languages that support both versions of the operators:
  * The _pre_-increment and _pre_-decrement operators increment (or decrement) their operand by 1, and the value of the expression is the _resulting_ incremented (or decremented) value.
  * The _post_-increment and _post_-decrement operators increase (or decrease) the value of their operand by 1, but the value of the expression is the operand's _original_ value prior to the increment (or decrement) operation.

## ASCII

* To find ASCII value of a character,

    ```c
    char chr = 'S';
    printf("%d\n", chr);
    ```

## If-else statement

* `if-else` ladder template

    ```c
    if (x > 1) {
    }
    else if(y > 0) {
    }
    else if (a && b) {
    }
    .
    .
    else {
    }
    ```

## `for` loop

* Structure

    ```c
    for (initializationStatement; testExpression; updateStatement) {
        // statements
    }
    ```

* Template

    ```c
    unsigned int i;
    for (i = 0; i < 4; i++) {
        print("for: %d\n", i);
    }
    ```

    In `for` loop argument `i++` and `++i` are equivalent because the counter `i` is incremented after the statements are executed.

## `while` loop

* Structure

    ```c
    while (testExpression) {
        // statements
    }
    ```

* Template

    ```c
    unsigned int i = 0;
    while (i < 4) {
        printf("while: %d\n", i);
        i++;
    }
    ```

* `do-while` loop

    ```c
    do {
    // statements
    }
    while (testExpression);
    ```

    This executes the statement first regardless of the _test value_. Only then, the test expression comes into action afterwards.

## `break` / `continue`

* The break statement _ends the loop immediately_ when it is encountered.

    ```c
    break;
    ```

* The continue statement _skips the current iteration_ of the loop and continues with the next iteration.

    ```c
    continue;
    ```

## `switch` statement

* Structure

    ```c
    switch (expression) ​{
        case constant1:
        // statements
        break;
        case constant2:
        // statements
        break;
        .
        .
        default:
        // default statements
        break;
    }
    ```

* Template

    ```c
    num = 0;
    switch (num) {
    case 1:
        printf("switch: %d\n", num);
        break;
    case 2:
        printf("switch: %d\n", num);
        break;
    default:
        printf("switch: %d\n", num);
        break;
    }
    ```

* Without `break;`, all statements after the matching label are executed.
* The default clause inside the `switch` statement is optional.

## `switch` and `break`

* Each `case` must be closed by `break;`.

    ```c
    case 1:
        // statements
        break;
    ```

## Array

### One dimensional array

* Declaration

    ```c
    dataType arrayName[arrSize];
    ```

    `arrayName` has arrSize _elements_. The _index_ starts from `0` and ends with `arrSize-1`.

* Initialization

    ```c
    int arr[5] = {0, 1, 2, 3, 4};
    ```

    ```c
    int arr[] = {0, 1, 2, 3, 4}; // declaration without specifying the size.
    ```

* Change value

    ```c
    arr[0] = 1;
    ```

### Multidimensional array

* Declaration

    ```c
    dataType arrayName[arrSize1][arrSize2]...;
    ```

* Initialization

    ```c
    int arr[2][3] = {{1, 3, 0}, {-1, 5, 9}}; // or
    int arr[][3] = {{1, 3, 0}, {-1, 5, 9}}; // or
    int arr[2][3] = {1, 3, 0, -1, 5, 9}; // or
    int arr2[][2][2] = { {{0, 1}, {2, 3}}, {{4, 5}, {6, 7}} };
    ```

## String

* String terminator `"\0"` is added at the end of the string when a string is defined.

## `printf` format string (% placeholder)

* [*cplusplus](http://www.cplusplus.com/reference/cstdio/printf/) [*wikipedia](https://en.wikipedia.org/wiki/Printf_format_string)

## Callback Function

* [*stackoverflow](https://stackoverflow.com/a/147241)

## Storage class specifier

* [*microsoft](https://docs.microsoft.com/en-us/cpp/c-language/c-storage-classes?view=vs-2019)
* auto, register, static, extern, typedef

## C Type Specifiers

* [*microsoft](https://docs.microsoft.com/en-us/cpp/c-language/c-type-specifiers?view=vs-2019)
