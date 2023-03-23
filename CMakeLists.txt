cmake_minimum_required(VERSION 3.15)

# this makes the automagic conan integration work
# NOTE: this is meant to be passed by the user on the command-line, not hardcoded here
set(CMAKE_PROJECT_TOP_LEVEL_INCLUDES cmake/conan_provider.cmake)

project(useglad)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(glad REQUIRED)
add_executable(useglad src/useglad.cpp)
target_link_libraries(useglad PRIVATE glad::glad)
