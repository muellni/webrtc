cmake_minimum_required(VERSION 2.6)
project(common_video)

file(GLOB src_file ./*.cc ./libyuv/*.cc ./h264/*.cc)

webrtc_add_library(common_video
  SOURCES ${src_file}
  INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}/../../third_party/libyuv/include
  LINK_LIBRARIES
    yuv
)
