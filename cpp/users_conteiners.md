- Коллекции на основе дерева поиска
- Коллекции на основе хэш таблиц



## Коллекции на основе хэш таблиц

Для того, чтобы добавить свой тип в хэш таблицу будь то unordered_set, будь то unordered_map необходимо определить для своего типа оператор ==, а так же определить хэш функцию. 

Пример

```c++
#include <limits>
#include <random>
#include <unordered_set>

using namespace std;

using CoordType = int;

struct Point3D {
  CoordType x;
  CoordType y;
  CoordType z;

  bool operator==(const Point3D& other) const {
    return x == other.x && y == other.y && z == other.z;
  }
};

struct Hasher {
  size_t operator()(const Point3D& point) const {
    // выбираем в качестве коэффициента довольно большое простое число;
    // свободный член можем положить равным нулю, т.к. он не влияет
    // на коллизии, а лишь циклически смещает бакеты
    const size_t coef = 2'946'901;

    const hash<CoordType> coord_hasher;

    return (
        coef * coef * coord_hasher(point.x) +
               coef * coord_hasher(point.y) +
                      coord_hasher(point.z)
    );
  }
};

int main()
{
    
  vector<Point3D> points = {
    {1, 2, 3},
    {0, 2, 3},
    {1, 0, 3},
    {1, 2, 0},
  };

  unordered_set<Point3D, Hasher> point_set;
    return 0;
}
```



```