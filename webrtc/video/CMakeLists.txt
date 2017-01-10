cmake_minimum_required(VERSION 2.6)
project(video)

file(GLOB src_file ./*.cc)

webrtc_add_library(video
  SOURCES ${src_file}
  DEPENDS
    module_video_coding
    module_pacing
    module_rtp_rtcp
    module_video_processing
    video_and_call
    voice_engine
  )
