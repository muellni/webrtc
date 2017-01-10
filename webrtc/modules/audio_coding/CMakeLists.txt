cmake_minimum_required(VERSION 2.6)
project(module_audio_coding)

file(GLOB lib_src ./acm2/*.cc ./codecs/*.cc ./codecs/isac/*.cc ./codecs/isac/main/source/*.c ./codecs/isac/main/source/*.cc ./codecs/isac/main/util/*.c ./codecs/isac/fix/source/*.cc ./codecs/isac/fix/source/*.c ./codecs/g711/*.cc ./codecs/g711/*.c ./codecs/cng/*.cc ./codecs/pcm16b/*.cc ./codecs/pcm16b/*.c ./neteq/*.cc )

webrtc_add_library(module_audio_coding
  SOURCES ${lib_src}
  INCLUDE_DIRECTORIES
    ${WEBRTC_ROOT_PATH}/webrtc/modules/audio_coding/codecs/isac/main/include
    ${WEBRTC_ROOT_PATH}/webrtc/common_audio/signal_processing/include
    ${WEBRTC_ROOT_PATH}/third_party/opus/celt
    ${WEBRTC_ROOT_PATH}/third_party/opus/src
    ${WEBRTC_ROOT_PATH}/third_party/opus/include
    ${CMAKE_CURRENT_SOURCE_DIR}/include
  DEPENDS
    common
    common_audio
  )
