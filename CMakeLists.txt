cmake_minimum_required(VERSION 3.9 FATAL_ERROR)
project(cmake_with_submodule VERSION 0.1)

set(BASE_URL "http://127.0.0.1:8000")

file(DOWNLOAD ${BASE_URL}/FindCriterion.cmake ${CMAKE_CURRENT_SOURCE_DIR}/FindCriterion.cmake)
file(DOWNLOAD ${BASE_URL}/criterion.cmake ${CMAKE_CURRENT_SOURCE_DIR}/criterion.cmake)
include(${CMAKE_CURRENT_SOURCE_DIR}/criterion.cmake)

add_criterion_test(tests tests/test_example.c)
