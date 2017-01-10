cmake_minimum_required(VERSION 2.6)
project(module_bitrate_controller)

file(GLOB src_file ./*.cc)

webrtc_add_library(module_bitrate_controller
  SOURCES ${src_file}
  INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}/include
  )
