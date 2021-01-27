cmake_minimum_required(VERSION 3.15)

project(supplemental_test_files VERSION 0.1.0 LANGUAGES CXX)

set(SUPPLEMENTAL_TEST_DATA_DIR ${CMAKE_CURRENT_BINARY_DIR})


# Copy static files to the build dir so they live alongside the generated ones
file(GLOB_RECURSE example_files RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} data/*.txt)
foreach(example_file ${example_files})
  configure_file(${example_file} ${example_file} COPYONLY)
endforeach(example_file)
