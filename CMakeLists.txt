# Minimum version can be no higher than 3.5 as Ubuntu package management uses this version.
cmake_minimum_required(VERSION 3.5)

project (EX09-ComplexNumbers)

set(SOURCE_PREFIX "complex")
set(EXEC_NAME "ComplexNumbers")

if(EXISTS ${CMAKE_HOME_DIRECTORY}/csv13-lib/CMakeLists.txt)
    include(csv13-lib/CMakeLists.txt)
else()
    add_custom_target(submodule-init ALL git submodule init COMMAND git submodule update --recursive WORKING_DIRECTORY ${CMAKE_SOURCE_DIR})
endif()