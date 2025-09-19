## Сортировка слиянием (merge sort)
```cpp
#include <iostream>
#include <vector>
std::vector<int> arr{4,3,2,4,5,2,1,5,0,10};

void merge(int left, int mid, int right) {
  int n1 = mid - left + 1; // +1 because of [0 1] 2
  int n2 = right - mid;
  std::vector<int>l(n1),r(n2);

  for (int i = 0; i < n1; i++) {
    l[i] = arr[left + i];
  }
  for (int i = 0; i < n2; i++) {
    r[i] = arr[mid + 1 + i];
  }

  int i = 0, j = 0, k = left;
  while (i < n1 && j < n2) {
    if (l[i] <= r[j]) {
      arr[k] = l[i];
      i++;
    }
    else {
      arr[k] = r[j];
      j++;
    }
      k++;
  }

  while (i < n1) {
    arr[k] = l[i];
    i++;
    k++;
  }

  while (j < n2) {
    arr[k] = r[j];
    j++;
    k++;
  }

}

void mergesort(int left, int right) {
  if (left >= right) {
    return;
  }
  int mid = left + (right - left) / 2;
  mergesort(left, mid);
  mergesort(mid + 1, right);
  
  //std::cout<<left<<" "<< mid << " " << right << std::endl;
  merge(left, mid, right);
}

int main() {
    mergesort(0, 9);
    // left = 0 - first element's index
    // right = 9 - last element's index
    for(int i = 0; i < 10; i++) {
      std::cout << arr[i] << " ";
    }
}
```

## Мастер теорема
Мастер теорема позволяет найти асимптотическое решение реккурнтных соотношений, которые могут возникнуть в анализе асимптотики многих алгоритмов.

Пусть имеются рекуррентные соотношения:
$$
T(n) = 
\begin{cases}
a \, T\!\left(\dfrac{n}{b}\right) + f(n^c), & n > 1, \\[1ex]
\Theta(1), & n = 1.
\end{cases}
$$
где: $a \in \mathbb{N}$, $b \in \mathbb{R}$, $b > 1$, $c \in \mathbb{R}^+$. Тогда асимптотическое решение имеет вид:
1. Если $c > \log_{b}a$, то $T(n) = O(n^c)$,
2. Если $c = \log_{b}a$, то $T(n) = O(n^c*\log n)$,
3. Если $c < \log_{b}a$, то $T(n) = O(n^{\log_{b} a})$.

## Ссылки (links):
1. [Мастер-теорема (Викиконспекты ИТМО)](https://neerc.ifmo.ru/wiki/index.php?title=Мастер-теорема)