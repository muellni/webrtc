cmake_minimum_required(VERSION 2.6)
project(module_video_capture)

set(src_com *.cc ./external/*.cc)
if (WEBRTC_LINUX)
  file(GLOB lib_src ./linux/*.cc ${src_com})
endif ()

webrtc_add_library(module_video_capture
  SOURCES ${lib_src}
  )
