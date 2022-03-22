## **Curiously Recurring Template Pattern** (**CRTP**)


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

