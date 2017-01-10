cmake_minimum_required(VERSION 2.6)
project(pc)

file(GLOB src_file ./*.cc)

webrtc_add_library(pc
  SOURCES ${src_file}
  DEPENDS
    p2p
    media
  )
