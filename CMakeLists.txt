cmake_minimum_required(VERSION 3.2)

project(rscode)

include_directories(${PROJECT_SOURCE_DIR})

file(GLOB librscode_sources ./*)

list(REMOVE_ITEM librscode_sources ${PROJECT_SOURCE_DIR}/example.c)

add_library(rscode STATIC ${librscode_sources})

set_target_properties(rscode
    PROPERTIES 
    COMPILE_FLAGS "-Wall -Wstrict-prototypes"
    ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib/${CMAKE_BUILD_TYPE}
    )
