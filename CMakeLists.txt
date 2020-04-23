cmake_minimum_required(VERSION 3.16)
project(librmcp VERSION 0.0.1 LANGUAGES C)

set(CMAKE_BUILD_TYPE Debug)
add_compile_options("-fsanitize=address")
add_compile_options("-fno-omit-frame-pointer")
link_libraries("-fsanitize=address -fno-omit-frame-pointer")

include_directories( include )
add_library(rmcp STATIC src/rmcp.c)
add_executable(print_ping src/print_ping.c)
target_link_libraries(print_ping rmcp)