cmake_minimum_required(VERSION 2.6)
project(module_video_coding)

file(GLOB src_file ./*.cc ./codecs/h264/*.cc ./codecs/i420/*.cc ./codecs/vp8/*.cc ./codecs/vp9/*.cc ./utility/*.cc)

webrtc_add_library(module_video_coding
  SOURCES ${src_file}
  INCLUDE_DIRECTORIES
    ${WEBRTC_ROOT_PATH}/third_party/libvpx
    ${WEBRTC_ROOT_PATH}/third_party/libyuv/include
  DEPENDS
    common_video
  )
