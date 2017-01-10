cmake_minimum_required(VERSION 2.6)
project(video_and_call)

file(GLOB src_file ./*.cc)

webrtc_add_library(video_and_call
  SOURCES ${src_file}
  )
