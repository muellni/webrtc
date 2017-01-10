cmake_minimum_required(VERSION 2.6)
project(voice_engine)

file(GLOB src_file ./*.cc)

webrtc_add_library(voice_engine
  SOURCES ${src_file}
  DEPENDS
    common_audio
    module_utility
    module_audio_processing
    #module_audio_device
    module_audio_conference_mixer
    call
  DEFINES
    WEBRTC_INCLUDE_INTERNAL_AUDIO_DEVICE
  )
