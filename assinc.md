## Простое решение проблем совместного доступа к одним данным

Как известно, ковырять одни и те же данные в разных потоках - не безопасная вещь. Но вот вопрос, что делать, если мы хотим по простому производить защиту данных? Простой способ сделать следующую обёртку

```
#include <mutex>
using namespace std;

template <typename T>
class Synchronized {
public:
  explicit Synchronized(T initial = T())
    : value(move(initial))
  {
  }

  struct Access {
    T& ref_to_value;
    lock_guard<mutex> guard;
  };

  Access GetAccess() {
    return {value, lock_guard(m)};
  }

private:
  T value;
  mutex m;
};
```

Что мы теперь имеем? Создаем объект Synchronized, и передаём через метод Access данные временной переменной. При вызове деструктора наш мьютекс освободится.