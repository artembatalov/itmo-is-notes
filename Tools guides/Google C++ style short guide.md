## Отступы и пробелы
- Используются только пробелы (2 пробела = отступ),
- После ключевых слов (if, for, etc) ставится пробел,
- Операторы окружены пробелами.

```cpp
#include <iostream>

int main() {
  int a = 5;
  if (a == 5) {
    cout << a;
  }
}
```

## Именование
- Переменные и функции: snake_case,
- Константы: kCamelCase с префиксом k.

```cpp
#include <iostream>

int main() {
  int example_variable = 5;
  const int example_of_constant_variable = 5;
}
```

## Фигурные скобки
- Открывающая скобка на той же строке.

```cpp
if (condition) {
  // ...
} else {
  // ...
}
```

## Длина строки
- Максимум 80 символов в строке.

```cpp
#include <iostream>

int main() {
  // This is 73 symbols:
  // aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa
}
```

## Указатели и ссылки
- Символ `*` или `&` ставится перед именем переменной (не после типа).

```cpp
#include <iostream>

int main() {
  int* ptr;
  const std::string& str;
}
```

## Комментарии
- Использовать `//` для комментариев.

```cpp
#include <iostream>

int main() {
  int a = 6;
  // Variablr a is not equal to 5 now
}
```
## Links
1. [Google C++ style guide from Google](https://google.github.io/styleguide/cppguide.html)