cmake_minimum_required(VERSION 2.6)
project(system_wrappers)

file(GLOB src_file ./source/*.c ./source/*.cc)

webrtc_add_library(system_wrappers
  SOURCES ${src_file}
  DEPENDS
    base
  )
