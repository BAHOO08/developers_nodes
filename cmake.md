# CMake

CMake — кроcсплатформенная утилита для автоматической сборки программы из исходного кода. 

[TOC]



## Простой пример

Код

```c++
#include <iostream>
int main(int argc, char** argv)
{
	std::cout << "Hello, World!" << std::endl;
	return 0;
}
```

Прописываем в CMakeLists.txt

```cmake
cmake_minimum_required(VERSION 3.22.2 FATAL_ERROR) # Проверка версии CMake.
									# Если версия установленой программы
									# старее указаной, произайдёт аварийный выход.
project(CMakeTest)
add_executable(main main.cpp)		# Создает исполняемый файл с именем main
									# из исходника main.cpp
```

Далее по простому генерируем проект


```bash
 mkdir build
 cd build
 cmake ..
```

В папке build появится по умолчанию сгенерированный проект под vs которая установлена на компе.

**Генерирование проекта осуществляется в сторонней папке, которая добавляется в gitignore**

Для сборки можем сделать:

```bash
cmake --build . --config Release
```

И запускаем

```bash.\Release\main.exe
Hello, World!
```

## Материалы

- [C++Now 2017: Daniel Pfeifer “Effective CMake" - YouTube](https://www.youtube.com/watch?v=bsXLMQ6WgIk)

- [Современный CMake: 10 советов по улучшению скриптов сборки / Хабр (habr.com)](https://habr.com/ru/post/330902/)

- [CppCon 2017: Mathieu Ropert “Using Modern CMake Patterns to Enforce a Good Modular Design” - YouTube](https://www.youtube.com/watch?v=eC9-iRN2b04)

  

