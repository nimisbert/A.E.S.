# Project :
cmake_minimum_required(VERSION 3.22.1)
project(cryptography)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")
include_directories(include)

# Libraries :
add_library(aes SHARED 
    src/galois256.c
    src/aes.c
    src/box.c
)

# Executables :
add_executable(galois256-test tests/galois256-test.c)
target_link_libraries(galois256-test aes)

add_executable(aes-test tests/aes-test.c)
target_link_libraries(aes-test aes)
