cmake_minimum_required(VERSION 2.6)
project(module_video_processing)

file(GLOB src_file ./*.cc ./util/*.cc)

webrtc_add_library(module_video_processing
  SOURCES ${src_file}
  )
