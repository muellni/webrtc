cmake_minimum_required(VERSION 2.6)
project(module_call)

file(GLOB src_file ./*.cc)

webrtc_add_library(call
  SOURCES ${src_file}
  INCLUDE_DIRECTORIES
    ${WEBRTC_ROOT_PATH}/webrtc
  DEPENDS
    module_rtp_rtcp
    video
    audio
    module_congestion_controller
)
