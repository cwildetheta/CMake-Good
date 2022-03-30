add_library(
    say-hello
    hello.hpp
    hello.cpp
)

target_include_directories(say-hello PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")