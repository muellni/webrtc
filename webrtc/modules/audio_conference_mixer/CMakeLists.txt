cmake_minimum_required(VERSION 2.6)
project(module_audio_conference_mixer)

include_directories()
file(GLOB lib_src ./source/*.cc)

webrtc_add_library(module_audio_conference_mixer
  SOURCES ${lib_src}
  INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}/include
  )
