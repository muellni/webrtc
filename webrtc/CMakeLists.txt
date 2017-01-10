include_directories(${CMAKE_SOURCE_DIR})

function(WEBRTC_ADD_LIBRARY libname)

  include(CMakeParseArguments)
  cmake_parse_arguments(ARG
  ""
  ""
  "SOURCES;INCLUDE_DIRECTORIES;LINK_LIBRARIES;DEPENDS;DEFINES"
  ${ARGN}
  )

  add_library(webrtc_${libname} STATIC ${ARG_SOURCES})
  target_link_libraries(webrtc_${libname}
    ${ARG_LINK_LIBRARIES})

  foreach(dep_lib IN LISTS ARG_DEPENDS)
    target_link_libraries(webrtc_${libname}
      webrtc_${dep_lib})
  endforeach()

  target_include_directories(webrtc_${libname}
    PRIVATE ${ARG_INCLUDE_DIRECTORIES}
    PRIVATE ${WEBRTC_ROOT_PATH})

  foreach(define IN LISTS ARG_DEFINES)
    target_compile_definitions(webrtc_${libname}
      PRIVATE ${define})
  endforeach()
endfunction()

file(GLOB src_files ./*.cc)

webrtc_add_library(common
  SOURCES ${src_files}
  )

add_subdirectory(api)
add_subdirectory(base)

add_subdirectory(p2p)
add_subdirectory(media)
add_subdirectory(audio)
add_subdirectory(video)
add_subdirectory(pc)
add_subdirectory(common_video)
add_subdirectory(common_audio)
add_subdirectory(system_wrappers)
add_subdirectory(voice_engine)
add_subdirectory(modules)
add_subdirectory(call)
add_subdirectory(video_and_call)

#file(GLOB src_files ./*.cc)

webrtc_add_library(full
  #SOURCES ${src_files}
  DEPENDS
    api
    audio
    base
    call
    common_audio
    common_video
    media
    module_audio_coding
    module_audio_conference_mixer
    module_audio_processing
    module_bitrate_controller
    module_congestion_controller
    module_media_file
    module_pacing
    module_remote_bitrate_estimator
    module_rtp_rtcp
    module_utility
    module_video_capture
    module_video_coding
    module_video_processing
    p2p
    pc
    system_wrappers
    video
    video_and_call
    voice_engine
)
