cmake_minimum_required(VERSION 3.5)
project(hellotest)

set(CMAKE_CXX_STANDARD 14)

set(INSTALL_GTEST OFF)
add_subdirectory(googletest)

set (BENCHMARK_ENABLE_INSTALL OFF)
set (BENCHMARK_ENABLE_TESTING OFF)
add_subdirectory(benchmark)

add_executable(hellotest hellotest.cpp)
target_link_libraries(hellotest gtest)

add_executable(hellobench hellobench.cpp)
target_link_libraries(hellobench benchmark)