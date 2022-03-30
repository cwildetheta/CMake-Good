cmake_minimum_required(VERSION 3.22.3)

project(CodeCMakeGood VERSION 1.0.0)

add_library(
    say-hello
    src/hello.hpp
    src/hello.cpp
)

add_executable(${PROJECT_NAME} src/main.cpp)

target_link_libraries(${PROJECT_NAME} PRIVATE say-hello)