## Ас сл алгоритма
#### Сортировка вставками
$O(n)=n ^ 2$

```cpp
int n = 4;  
vector<int>v{1, 3, 4, 2};

for(int i = 0; i < n; i++) {  
    for(int j = 0; j < n; j++) {  
        if(v[j] > v[j + 1]){  
            swap(v[j], v[j + 1]);  
        }  
    }  
}
```
