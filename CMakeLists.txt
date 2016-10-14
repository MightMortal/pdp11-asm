cmake_minimum_required(VERSION 3.6)
project(pdp11-asm)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES src/main.cpp)
set(SOURCE_FILES ${SOURCE_FILES} src/address.h)
set(SOURCE_FILES ${SOURCE_FILES} src/binary.h)
set(SOURCE_FILES ${SOURCE_FILES} src/command.h)
set(SOURCE_FILES ${SOURCE_FILES} src/compiler.h)
set(SOURCE_FILES ${SOURCE_FILES} src/data.h)
set(SOURCE_FILES ${SOURCE_FILES} src/label.h)
set(SOURCE_FILES ${SOURCE_FILES} src/labels_stor.h)
set(SOURCE_FILES ${SOURCE_FILES} src/operand.h)
set(SOURCE_FILES ${SOURCE_FILES} src/section.h)
set(SOURCE_FILES ${SOURCE_FILES} src/string.h)

add_executable(pdp11-asm-dbg ${SOURCE_FILES})
add_executable(pdp11-asm-deploy ${SOURCE_FILES})

set_target_properties(pdp11-asm-deploy
        PROPERTIES
        RUNTIME_OUTPUT_NAME "pdp11-asm"
        ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_CURRENT_LIST_DIR}/build"
        LIBRARY_OUTPUT_DIRECTORY "${CMAKE_CURRENT_LIST_DIR}/build"
        RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_LIST_DIR}/build")

