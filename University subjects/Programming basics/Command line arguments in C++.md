## Синтаксис
```cpp
#include <iostream>

int main(int argc, char* argv[]) {

}
```
## Суть
argc и argv предоставляют механизм параметризованного запуска программ.
## Использование через terminal
```bash
# Обычный запуск:
./main
# Запуск с аргументом Artem
./main Artem $(cat args.txt)
# Запуск с аргументами из файла
```

