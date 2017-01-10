cmake_minimum_required(VERSION 2.6)
project(api)

if (CMAKE_SYSTEM_NAME STREQUAL "Darwin")
  #include_directories(/usr/local/Cellar/openssl/1.0.2h_1/include)
endif ()

file(GLOB lib_src *.cc)

webrtc_add_library(api
  SOURCES ${lib_src}
)
