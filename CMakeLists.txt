cmake_minimum_required(VERSION 2.8.11)

#-------------------------------------------------------------------------------
# Initialize
#-------------------------------------------------------------------------------
project(avl_tree)
set(CMAKE_DISABLE_IN_SOURCE_BUILD ON)
 
#-------------------------------------------------------------------------------
# gtest
#-------------------------------------------------------------------------------
set(GTEST "${CMAKE_SOURCE_DIR}/deps/googletest/")
set(GTEST_BINARY_DIR "${CMAKE_BINARY_DIR}/deps/googletest/")
add_subdirectory("${GTEST}" "${GTEST_BINARY_DIR}")
 
#-------------------------------------------------------------------------------
# Compiler options
#-------------------------------------------------------------------------------
add_definitions(-Wall -Wextra -Werror -Wno-unused-parameter -std=c++17 -g -fPIC)

#-------------------------------------------------------------------------------
# Build tests
#-------------------------------------------------------------------------------
include_directories(
  ${CMAKE_SOURCE_DIR}
)

add_executable(avl-tree-tests
  test/unit.cc
)

target_link_libraries(avl-tree-tests
  gtest_main
)

