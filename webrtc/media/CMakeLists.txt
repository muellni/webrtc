cmake_minimum_required(VERSION 2.6)
project(media)


if (CMAKE_SYSTEM_NAME MATCHES "Darwin")
#  include_directories(/usr/local/Cellar/openssl/1.0.2h_1/include)
  include_directories(/usr/local/Cellar/gtk+/2.24.30/include/gtk-2.0/)
  include_directories(/usr/local/Cellar/glib/2.46.2/include/glib-2.0/)
  include_directories(/usr/local//Cellar/glib/2.46.2/lib/glib-2.0/include/)
  include_directories(/usr/local//Cellar/cairo/1.14.6_1/include/cairo/)
  include_directories(/usr/local//Cellar/pango/1.38.1/include/pango-1.0/)
  include_directories(/usr/local//Cellar/gtk+/2.24.30/lib/gtk-2.0/include/)
  include_directories(/usr/local//Cellar/gdk-pixbuf/2.32.3/include/gdk-pixbuf-2.0/)
  include_directories(/usr/local//Cellar/atk/2.18.0_1/include/atk-1.0/)
  include_directories(/Applications/Xcode.app/Contents/Developer//Platforms/MacOSX.platform/Developer/SDKs/MacOSX10.11.sdk/System/Library/Frameworks/Carbon.framework/Versions/A/Headers/)
elseif (CMAKE_SYSTEM_NAME STREQUAL "Linux")
  include_directories(/usr/include/gtk-2.0/)
  include_directories(/usr/include/glib-2.0/)
  include_directories(/usr/lib/x86_64-linux-gnu/glib-2.0/include/)
  include_directories(/usr/include/cairo/)
  include_directories(/usr/include/pango-1.0/)
  include_directories(/usr/lib/x86_64-linux-gnu/gtk-2.0/include/)
  include_directories(/usr/include/gdk-pixbuf-2.0/)
  include_directories(/usr/include/atk-1.0/)
endif ()

#file(GLOB src_file ./base/*.cc ./devices/*.cc ./engine/*.cc )
file(GLOB src_file ./base/*.cc  ./engine/*.cc )

webrtc_add_library(media
  SOURCES ${src_file}
  INCLUDE_DIRECTORIES
    ${CMAKE_CURRENT_SOURCE_DIR}/../../third_party/libyuv/include
  DEFINES
    DISABLE_MEDIA_ENGINE_FACTORY

)
