cmake_minimum_required(VERSION 2.6)
project(common_audio)

file(GLOB src_file ./*.cc ./*.c ./vad/*.cc ./vad/*.c ./resampler/*.cc ./signal_processing/*.c)

webrtc_add_library(common_audio
  SOURCES ${src_file}
  DEPENDS
    system_wrappers
)
