cmake_minimum_required(VERSION 3.14)

set (INCLUDEDIR include/)
set (SRCDIR src/)

SET(CMAKE_CXX_FLAGS "-Wall -g -ggdb3")

project(CallGraph)

add_library(libparser SHARED ${SRCDIR}/parser.cpp ${SRCDIR}/lib.cpp)
target_include_directories(libparser PRIVATE ${INCLUDEDIR})

add_executable(CallGraph ${SRCDIR}/main.cpp ${SRCDIR}/lib.cpp ${SRCDIR}/parser.cpp)

target_include_directories(CallGraph PRIVATE ${INCLUDEDIR})
