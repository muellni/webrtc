cmake_minimum_required(VERSION 2.6)
project(webrtc_base)

if (CMAKE_SYSTEM_NAME STREQUAL "Darwin")
  include_directories(/usr/local/Cellar/openssl/1.0.2h_1/include)
  include_directories(/opt//X11/include/)
endif ()

file(GLOB lib_src *.cc)

webrtc_add_library(base
  SOURCES ${lib_src}
  INCLUDE_DIRECTORIES
    ${WEBRTC_ROOT_PATH}/webrtc
)
