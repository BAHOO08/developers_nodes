## Chaining method

Прием method chaining позволяет сократить этот код т.к с помощью него можно подряд вызывать методы. Для этого мы в  каждом нашем методе возвратим ссылку на наш объект и выстроим вызовы в  цепочку 

```c++
class worker
{
	public:
	worker& set_data(const data_t& d){...; return *this;}
	worker& process(){...; return *this;}
	worker& send_result(){...; return *this;}
	worker& print_log(){...; return *this;}
	...
};

void foo()
{
	worker w;
	w.set_data(data_t{}).process().send_result().print_log();
	...
}
```

## Возможная проблема

Возможно нестандартное поведение

```c++
struct worker 
{
    worker& process(int& i)
    {
        i = 185;
        return *this;
    }
    worker& print_result(const int& i)
    {
        std::cout <<"result: "<< i << std::endl;
        return *this; 
    }
};

int main()
{
    int data = 0;
    worker w;
    w.process(data).print_result(data+2);
}
```
