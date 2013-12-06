cmake_minimum_required(VERSION 2.8)

add_definitions(-std=c++11)
set(CMAKE_CXX_FLAGS "-g -Wall")

set(sources main.cpp)
add_executable(test ${sources})
