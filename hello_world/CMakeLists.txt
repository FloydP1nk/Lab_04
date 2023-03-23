cmake_minimum_required(VERSION 3.22.1 FATAL_ERROR)
project(hello_world)
include_directories("/Users/pavelerokhin/Lab_04/formatter_lib/src")
include_directories("/Users/pavelerokhin/Lab_04/formatter_ex_lib/src")
add_library(formatter_lib STATIC "/Users/pavelerokhin/Lab_04/formatter_lib/src/formatter.cpp")
add_library(formatter_ex_lib STATIC "~/formatter_ex_lib/src/formatter_ex.cpp")
target_include_directories(formatter_ex_lib PUBLIC
${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib/src
)
add_executable(hello_exec "/Users/pavelerokhin/hello_world/src/hello_world.cpp")
target_link_libraries(hello_exec formatter_lib formatter_ex_lib)
