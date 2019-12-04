cmake_minimum_required(VERSION 3.9)

# Project name and a few useful settings. Other commands can pick up the results
project(RnnNoise
    VERSION 0.1
    DESCRIPTION "Noise suppression algorithm developed by Mozilla."
    LANGUAGES C CXX)

option(BUILD_EXAMPLES "Compiles the examples." OFF)

add_subdirectory(src)

if(BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()
