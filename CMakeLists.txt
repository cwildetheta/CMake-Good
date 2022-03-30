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

set(list_part_2 4 5 6)
set(target DIRECTORY "${PROJECT_SOURCE_DIR}")
set_property(
    ${target}
    PROPERTY TEST_VALUES
    1
    2
    3
    "${list_part_2}"
)

get_cmake_property(test_values_list TEST_VALUES)
message(STATUS "The values in the list are ${test_values_list}.")

function(sum out a b)
    math(EXPR ret "${a} + ${b}")
    set("${out}" "${ret}" PARENT_SCOPE)
endfunction()
function(product out a b)
    math(EXPR ret "${a} * ${b}")
    set("${out}" "${ret}" PARENT_SCOPE)
endfunction()

sum(value_1 3 5)
product(value_2 3 5)

message(STATUS "The sum of 3 and 5 is ${value_1} and the product is ${value_2}.")

add_subdirectory(say-hello)
add_subdirectory(src)