cmake_minimum_required(VERSION 2.6)
project(module_media_file)

file(GLOB src_file ./*.cc)

webrtc_add_library(module_media_file
  SOURCES ${src_file}
  DEPENDS
    common_audio
  )
