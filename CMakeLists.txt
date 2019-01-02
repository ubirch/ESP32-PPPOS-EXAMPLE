# The following lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

#set(CMAKE_VERBOSE_MAKEFILE 1)
#set(DEBUG 1)

# check and set the IDF_PATH
message(STATUS "$ENV{IDF_PATH}")
if (NOT DEFINED ENV{IDF_PATH})
    if (EXISTS "$ENV{HOME}/.idf")
        file(STRINGS "$ENV{HOME}/.idf" IDF_PATH)
        set(ENV{IDF_PATH} ${IDF_PATH})
    else ()
        message(FATAL_ERROR "ESP-IDF: set $IDF_PATH environment variable or write path to file $ENV{HOME}/.idf")
    endif ()
else ()
    set(IDF_PATH $ENV{IDF_PATH})
endif ()
message(STATUS "IDF_PATH: ${IDF_PATH}")

include($ENV{IDF_PATH}/tools/cmake/project.cmake)

# now configure the project
project(esp32-pppos-example)