cmake_minimum_required(VERSION 3.22.3)

project(CodeCMakeGood VERSION 1.0.0)

set(MY_VARIABLE_1 "Setting up the project:")
set(MY_VARIABLE_2 "     Project version:")
message(STATUS "${MY_VARIABLE_1} ${PROJECT_NAME} ${MY_VARIABLE_2} ${PROJECT_VERSION}")

add_subdirectory(say-hello)
add_subdirectory(src)