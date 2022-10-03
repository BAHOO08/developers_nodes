## Идиома immediately invoked lambda expression (IILE)

Суть ее в том, что для инициализации константного объекта мы создаем lambda-функцию и тут же, рядом с тем местом,
где мы ее создали, мы ее вызываем.
Таким образом, вызывая вот эту вот лямбду в месте ее создания, мы можем не терять константность.

```c++
int main() {
const vector<int> sorted_numbers = [] {
vector<int> data = Sorted({5, 4, 2, 1, 5, 1, 3, 4, 5, 6, 8});
auto it = unique(begin(data), end(data));
data.erase(it, end(data));
return data;
}();
```

#[[cpp]] 