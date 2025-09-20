## Затемнение переменных
Локальные переменные имеют приоритет в случае наличия глобальных дубликатов, поэтому этот код работает:
```cpp
#include <iostream>

int x;
int y;
void func(double x) {
    double y;
    std::cout << "x = " << x << " y = " << y << std::endl;
}

int main() {
    x = 21;
    {
        int x = 10;
        y = 239;
        std::cout << "x = " << x << " y = " << y << std::endl;
        func(y);
    }
    std::cout << "x = " << x << " y = " << y << std::endl;
    return 0;
}
```
## Pointer (Указатель)
Указатель - переменная, диапазон значений которой состоит из адресов ячеек памяти и нулевого адреса.

Операторы для работы с указателями:
1. Унарный оператор: & (выдаёт адрес объекта),
2. Унарный оператор: * (выдаёт объект косвенно).

```cpp
#include <iostream>  
#include <vector>  
using namespace std;  
  
int main() {  
    int a = 5;  
    int* adres = &a;  
  
    cout << adres << " " << a << endl;  
    // 0x16b65b28c 5  
}
```

Адрес можно получить у любой переменной, при этом размер этой переменной с адресом постоянен и не зависит от размера типа переменной.

```cpp
#include <iostream>  
#include <vector>  
using namespace std;  
  
void change(int* adr_a, int* adr_b) {  
    int tmp = *adr_a;  
    *adr_a = *adr_b;  
    *adr_b = tmp;  
}  
  
int main() {  
    int x = 1, y = 2;  
    change(&x, &y);  
    cout << x << " " << y << endl;  
}
```
## Массивы и указатели
Использование `*(pa + i)`, где pa - указатель на первый элемент массива, то это выражение эквивалентно `a[i]`. P. S. Вычитать указатели иногда имеет смысл.
## Строки и указатели
