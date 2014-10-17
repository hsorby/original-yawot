
cmake_minimum_required (VERSION 2.8)

set(PROJECT_NAME Yawot)
project(${PROJECT_NAME})

# The version number.
set(YAWOT_VERSION_MAJOR 0)
set(YAWOT_VERSION_MINOR 1)
set(YAWOT_VERSION_PATCH 0)
set(LIBRARY_VERSION 0x${YAWOT_VERSION_MAJOR}${YAWOT_VERSION_MINOR}${YAWOT_VERSION_PATCH}

set(VERSION_CONFIG_IN "${PROJECT_SOURCE_DIR}/src/configure/version.in.h")
set(HEADER_FILES ${PROJECT_SOURCE_DIR}/src/api/yawot/version.h ${VERSION_CONFIG_IN})
set(SOURCE_FILES ${PROJECT_SOURCE_DIR}/src/version.cpp)

include_directories("${PROJECT_BINARY_DIR}/src" "${PROJECT_SOURCE_DIR}/src/api" "${PROJECT_BINARY_DIR}/src")

set(VERSION_CONFIG "${PROJECT_BINARY_DIR}/src/configure/version.h")
configure_file (
  ${VERSION_CONFIG_IN}
  ${VERSION_CONFIG}
)

set(LIBRARY_NAME yawot)
add_library(${LIBRARY_NAME} ${SOURCE_FILES} ${HEADER_FILES} ${VERSION_CONFIG})

