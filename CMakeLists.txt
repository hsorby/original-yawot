
cmake_minimum_required (VERSION 2.8)

set(PROJECT_NAME Yawot)
project(${PROJECT_NAME})

# The version number.
set (YAWOT_VERSION_MAJOR 0)
set (YAWOT_VERSION_MINOR 1)
set (YAWOT_VERSION_PATCH 0)

set(HEADER_FILES ${PROJECT_SOURCE_DIR}/src/api/yawot/version.h)
set(SOURCE_FILES ${PROJECT_SOURCE_DIR}/src/version.cpp)

include_directories("${PROJECT_BINARY_DIR}/src" "${PROJECT_SOURCE_DIR}/src/api")

set(LIBRARY_NAME yawot)
add_library(${LIBRARY_NAME} ${SOURCE_FILES} ${HEADER_FILES})

