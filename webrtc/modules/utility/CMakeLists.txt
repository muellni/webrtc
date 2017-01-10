cmake_minimum_required(VERSION 2.6)
project(module_utility)

file(GLOB src_file ./source/*.cc)

webrtc_add_library(module_utility
  SOURCES ${src_file}
  DEPENDS
    module_audio_coding
    module_media_file
  )
