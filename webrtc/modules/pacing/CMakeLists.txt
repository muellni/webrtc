cmake_minimum_required(VERSION 2.6)
project(module_pacing)

file(GLOB src_file ./*.cc)

webrtc_add_library(module_pacing
  SOURCES ${src_file}
  )
