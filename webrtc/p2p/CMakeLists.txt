cmake_minimum_required(VERSION 2.6)
project(p2p)

#file(GLOB lib_src ./base/*.cc ./client/*.cc ./quic/*.cc ./stunprober/*.cc)
file(GLOB lib_src ./base/*.cc ./client/*.cc  ./stunprober/*.cc)


webrtc_add_library(p2p
  SOURCES ${lib_src}
  INCLUDE_DIRECTORIES
    ${WEBRTC_ROOT_PATH}/chromium/src
  )
