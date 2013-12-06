cmake_minimum_required(VERSION 2.8)
project(log4cxx_example)

add_definitions(-std=c++11)
set(CMAKE_CXX_FLAGS "-g -Wall")

set(sources main.cpp)
add_executable(test ${sources})

function(test_lib LIB_NAME)
  if (${LIB_NAME} MATCHES "^.*-NOTFOUND")
    message(FATAL_ERROR "lib not found: " ${LIB_NAME} " check README")
    return()
  endif(${LIB_NAME} MATCHES "^.*-NOTFOUND")
endfunction(test_lib)

# LOG4CXX
find_library(LOG log4cxx)
test_lib(${LOG})

target_link_libraries(test ${LOG})
