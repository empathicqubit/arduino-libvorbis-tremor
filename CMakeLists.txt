cmake_minimum_required(VERSION 3.16)

# set the project name
project(arduino_libvorbis C)

# we use FetchContent to install 
include(FetchContent)

# lots of warnings and all warnings as errors
## add_compile_options(-Wall -Wextra )

file(GLOB_RECURSE SRC_LIST_C CONFIGURE_DEPENDS  "${PROJECT_SOURCE_DIR}/*.c" )

# define libraries
add_library (arduino_libvorbis ${SRC_LIST_C})

target_link_libraries(arduino_libvorbis PRIVATE arduino_libopus)

target_include_directories(arduino_libvorbis PUBLIC "../arduino_libopus/src")
# define location for header files
target_include_directories(arduino_libvorbis PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/src )