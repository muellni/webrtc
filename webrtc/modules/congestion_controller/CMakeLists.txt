cmake_minimum_required(VERSION 2.6)
project(congestion_controller)

file(GLOB src_file ./*.cc)

webrtc_add_library(module_congestion_controller
  SOURCES ${src_file}
  DEPENDS
    module_remote_bitrate_estimator
    module_bitrate_controller
  )
