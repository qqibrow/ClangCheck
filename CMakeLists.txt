cmake_minimum_required(VERSION 2.8)
project(TestClangChecker)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp)
add_executable(TestClangChecker ${SOURCE_FILES})
