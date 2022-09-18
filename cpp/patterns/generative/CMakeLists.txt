cmake_minimum_required(VERSION 3.5)

project(gof_1)

add_executable(abstract_factory abstract_factory.cpp)
add_executable(builder builder.cpp)
add_executable(dependency_injection dependency_injection.cpp)
add_executable(factory_method factory_method.cpp)
add_executable(lazy_initialization lazy_initialization.cpp)
add_executable(multiton multiton.cpp)
add_executable(object_pool object_pool.cpp)
add_executable(prototype prototype.cpp)
add_executable(singleton singleton.cpp)

set_target_properties(abstract_factory builder dependency_injection factory_method lazy_initialization multiton object_pool prototype singleton PROPERTIES
    CXX_STANDARD 14
    CXX_STANDARD_REQUIRED ON
    )
