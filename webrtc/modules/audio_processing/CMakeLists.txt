cmake_minimum_required(VERSION 2.6)
project(module_audio_processing)

file(GLOB src_file ./*.cc ./aec/*.cc ./agc/*.cc ./agc/legacy/*.c ./beamformer/*.cc ./intelligibility/*.cc ./transient/*.cc ./vad/*.cc ./ns/*.c ./aecm/*.cc ./utility/*.cc)

webrtc_add_library(module_audio_processing
  SOURCES ${src_file}
  INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}/include
  )
