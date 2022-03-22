## **Curiously Recurring Template Pattern** (**CRTP**)

Суть ее в том, что для инициализации константного объекта мы создаем lambda-функцию и тут же, рядом с тем местом,
где мы ее создали, мы ее вызываем.
Таким образом, вызывая вот эту вот лямбду в месте ее создания, мы можем не терять константность.

```c++
template<class T>
class Base
{
    // methods within Base can use template to access members of Derived
};
class Derived : public Base<Derived>
{
    // ...
};
```

