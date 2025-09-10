## Check your installation
1. VS Code,
2. C/C++ (from Microsoft).

## Starting the project
1. Create new folder and open it as a new project in VS Code.
2. Create main.cpp file with simple code. Pattern
```cpp
#include <iostream>

int main() {
	std::cout << "Hello, world!" << std::endl;
}
```
## Hand compilation via terminal
1. Open terminal (cmd + shift + `),
2. Write the command to compile your file:
```bash
clang++ -std=c++17 -g main.cpp -o main
```
(clang++ - compiler's command; -std=c++17 - language's standart; -g - flag for generating debugging information; main.cpp - name of file that need to be compiled; -o main - flag and name of executable file).
3. To run the code, write:
```bash
./main
```