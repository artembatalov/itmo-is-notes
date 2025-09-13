## About identifiers
- letters and numbers are possible to use,
- first letter is a letter or _ only,
- can't be the same is language words,
- good naming is crucial.

## Data types

| Type                | Size (bytes) | Value Range (Min - Max)                                  |
|---------------------|--------------|----------------------------------------------------------|
| **Boolean**         |              |                                                          |
| `bool`              | 1            | `false` or `true`                                        |
| **Character Types** |              |                                                          |
| `char`              | 1            | -128 to 127 or 0 to 255 (implementation-defined)         |
| `signed char`       | 1            | -128 to 127                                              |
| `unsigned char`     | 1            | 0 to 255                                                 |
| `wchar_t`           | 2 or 4       | 0 to 65,535 or -2,147,483,648 to 2,147,483,647           |
| `char16_t`          | 2            | 0 to 65,535                                              |
| `char32_t`          | 4            | 0 to 4,294,967,295                                       |
| **Integer Types**   |              |                                                          |
| `short`             | 2            | -32,768 to 32,767                                        |
| `unsigned short`    | 2            | 0 to 65,535                                              |
| `int`               | 4            | -2,147,483,648 to 2,147,483,647                          |
| `unsigned int`      | 4            | 0 to 4,294,967,295                                       |
| `long`              | 4 or 8       | -2,147,483,648 to 2,147,483,647 or ≈±9.2×10¹⁸           |
| `unsigned long`     | 4 or 8       | 0 to 4,294,967,295 or 0 to ≈1.8×10¹⁹                     |
| `long long`         | 8            | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `unsigned long long`| 8            | 0 to 18,446,744,073,709,551,615                          |
| **Fixed-width Integers** |          |                                                          |
| `int8_t`            | 1            | -128 to 127                                              |
| `uint8_t`           | 1            | 0 to 255                                                 |
| `int16_t`           | 2            | -32,768 to 32,767                                        |
| `uint16_t`          | 2            | 0 to 65,535                                              |
| `int32_t`           | 4            | -2,147,483,648 to 2,147,483,647                          |
| `uint32_t`          | 4            | 0 to 4,294,967,295                                       |
| `int64_t`           | 8            | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 |
| `uint64_t`          | 8            | 0 to 18,446,744,073,709,551,615                          |
| **Floating-point Types** |          |                                                          |
| `float`             | 4            | ≈±1.2×10⁻³⁸ to ≈±3.4×10³⁸, 6-9 significant digits        |
| `double`            | 8            | ≈±2.2×10⁻³⁰⁸ to ≈±1.8×10³⁰⁸, 15-17 significant digits    |
| `long double`       | 8, 12, or 16 | Range and precision vary by implementation               |
| **Void**            |              |                                                          |
| `void`              | N/A          | No storage; used for functions without return value      |

### Numeric limits
Checking data types:
```cpp
#include <iostream>
#include <limits>

int main() {
    // Для целых чисел
    std::cout << "int min: " << std::numeric_limits<int>::min() << std::endl;
    std::cout << "int max: " << std::numeric_limits<int>::max() << std::endl;
    
    // Для чисел с плавающей точкой
    std::cout << "float min: " << std::numeric_limits<float>::min() << std::endl;
    std::cout << "float max: " << std::numeric_limits<float>::max() << std::endl;
    std::cout << "float epsilon: " << std::numeric_limits<float>::epsilon() << std::endl;
    
    return 0;
}
```
### Integer literals
```cpp
#include <iostream>

int main(int argc, char** argv) {
  int a = 162;
  int b = 0242; // OCT
  int c = 0xA2; // HEX
  int d = 0b1010101; // BIN
  std::cout << "d = " << d << std::endl;
}
```
### Float literals
```cpp
#include <iostream>

int main(int argc, char** argv) {
  double a = 0.15;
  float b = 0.15f; // 0.15f - float type, 0.15 - double type
  long double c = 15e - 2l;
  float d = 15e - 2f;
  std::cout << "a = " << a << std::endl
			<< "b = " << b << std::endl
			<< "c = " << c << std::endl
			<< "d = " << d << std::endl;
}
```
### Data representation in computer memory
E. g. 1: int8_t:

| 7   | 00000111      |
| --- | ------------- |
| -7  | **111111001** |

### Symbolic literals

| Escape Sequence | Name                        | Description                                                      | Decimal Value (ASCI) |
| --------------- | --------------------------- | ---------------------------------------------------------------- | -------------------- |
| `\a`            | Alert (Bell)                | Produces an audible or visible alert                             | 7                    |
| `\b`            | Backspace                   | Moves the cursor back one position                               | 8                    |
| `\f`            | Form Feed                   | Advances to the next page or form                                | 12                   |
| `\n`            | New Line (Line Feed)        | Moves the cursor to the beginning of the next line               | 10                   |
| `\r`            | Carriage Return             | Moves the cursor to the beginning of the current line            | 13                   |
| `\t`            | Horizontal Tab              | Inserts a horizontal tab space                                   | 9                    |
| `\v`            | Vertical Tab                | Inserts a vertical tab space                                     | 11                   |
| `\\`            | Backslash                   | Inserts a backslash character                                    | 92                   |
| `\'`            | Single Quote                | Inserts a single quotation mark                                  | 39                   |
| `\"`            | Double Quote                | Inserts a double quotation mark                                  | 34                   |
| `\?`            | Question Mark               | Inserts a question mark (used to avoid trigraph interpretation)  | 63                   |
| `\0`            | Null Character              | Represents the null terminator (end of string marker)            | 0                    |
| `\ooo`          | Octal Escape Sequence       | Character represented by 1-3 octal digits (e.g., `\101` = 'A')   | ooo                  |
| `\xhh`          | Hexadecimal Escape Sequence | Character represented by hexadecimal digits (e.g., `\x41` = 'A') | hh                   |

### Enum
User data type for limited set of constants
```cpp
enum Color : int8_t {
  RED;
  GREEN;
  BLUE
};

Color color = Color::BLUE;
```
### Data declaration and definition
```cpp
int a; // a is declarated
a = 10; // a is defined
```
## Operators
- Arithmetic: +, -, /,
- Logical: ||, &&,
- etc.

## Sizeof
```cpp
#include <iostream>

int main(int argc, char** argv) {
  int a = 1;
  std::cout << sizeof(a); // 4
}
```
