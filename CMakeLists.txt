cmake_minimum_required(VERSION 3.22.3)

project(CodeCMakeGood VERSION 1.0.0)

set(MY_VARIABLE_1 "Setting up the project:")
set(MY_VARIABLE_2 "     Project version:")
message(STATUS "${MY_VARIABLE_1} ${PROJECT_NAME} ${MY_VARIABLE_2} ${PROJECT_VERSION}")

if(${PROJECT_VERSION} STREQUAL 1.0.0)
    message(STATUS "You know you're meant to update the version at some point right?")
else()
    message(STATUS "Good job remembering to update the version.")
endif()

set(MY_VALUE 0)
while(MY_VALUE LESS 101)
    message(STATUS "Set up preperation ${MY_VALUE}% done.")
    math(EXPR MY_VALUE "${MY_VALUE} + 25")
endwhile()

foreach(idx RANGE 0 100 25)
    message(STATUS "Set up ${idx}% done.")
endforeach()

add_subdirectory(say-hello)
add_subdirectory(src)