cmake_minimum_required(VERSION 2.6)
project(rtp_rtcp)

file(GLOB src_file ./source/*.cc ./source/rtcp_packet/*.cc)

webrtc_add_library(module_rtp_rtcp
  SOURCES ${src_file}
  DEPENDS
    common_video
  )
