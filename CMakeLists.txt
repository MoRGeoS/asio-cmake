cmake_minimum_required(VERSION 3.19)
project(asio)

file(GLOB_RECURSE HEADER_FILES CONFIGURE_DEPENDS
  ${CMAKE_CURRENT_SOURCE_DIR}/include/*.hpp
)

add_library(asio
  INTERFACE
    ${HEADER_FILES}
)

set_target_properties(asio
  PROPERTIES
    CXX_STANDARD 20
    CXX_STANDARD_REQUIRED ON
    CXX_EXTENSIONS ON
)

target_include_directories(asio
  INTERFACE
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)