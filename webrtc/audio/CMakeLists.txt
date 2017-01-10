cmake_minimum_required(VERSION 2.6)
project(audio)


include_directories(${CMAKE_SOURCE_DIR})

file(GLOB src_files ./*.cc)

webrtc_add_library(audio
  SOURCES ${src_files}
)
