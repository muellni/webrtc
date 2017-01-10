cmake_minimum_required(VERSION 2.6)
project(module_remote_bitrate_estimator)

file(GLOB src_file ./*.cc)

webrtc_add_library(module_remote_bitrate_estimator
  SOURCES ${src_file}
  )
