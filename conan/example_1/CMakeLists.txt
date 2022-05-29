cmake_minimum_required(VERSION 3.16)
project(FMT_example)

add_definitions("-std=c++17")
set(CMAKE_CXX_STANDART 17)
set(CMAKE_MODULE_PATH "${CMAKE_BINARY_DIR};${CMAKE_MODULE_PATH}")

set(PROJECT_NAME "fmt_example")

include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME} ${CONAN_LIBS})