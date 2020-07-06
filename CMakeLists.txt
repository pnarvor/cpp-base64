cmake_minimum_required(VERSION 3.10)
project(cpp_base64 VERSION 0.1)

list(APPEND cpp_base64_headers
    include/base64/base64.h
)
add_library(cpp_base64 SHARED
    src/base64.cpp
)
set_target_properties(cpp_base64 PROPERTIES
    PUBLIC_HEADER "${cpp_base64_headers}"
)
target_include_directories(cpp_base64 PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

include(${CMAKE_CURRENT_SOURCE_DIR}/cmake/installation.cmake)
install_target(cpp_base64)
