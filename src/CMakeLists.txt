cmake_minimum_required(VERSION 3.7)
project(Beldas-Adventure VERSION 1.0)

# Generates a `compile_commands.json` that can be used for autocompletion
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(OSBitness 32)
if(CMAKE_SIZEOF_VOID_P EQUAL 8)
    set(OSBitness 64)
endif()

# set (FullOutputDir "${CMAKE_SOURCE_DIR}/build/${CMAKE_SYSTEM_NAME}${OSBitness}/${CMAKE_BUILD_TYPE}")
# set (CMAKE_ARCHIVE_OUTPUT_DIRECTORY "${FullOutputDir}/static libs")
# set (CMAKE_LIBRARY_OUTPUT_DIRECTORY "${FullOutputDir}")
# set (CMAKE_RUNTIME_OUTPUT_DIRECTORY "${FullOutputDir}")

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIRS})

add_executable(Beldas-Adventure main.c)
target_link_libraries(Beldas-Adventure ${SDL2_LIBRARIES})
