cmake_minimum_required (VERSION 3.8.1)

file(GLOB IMGUI_SRC ${CMAKE_CURRENT_SOURCE_DIR}/imgui/*.cpp)
file(GLOB IMGUI_HEAD ${CMAKE_CURRENT_SOURCE_DIR}/imgui/*.h)

# imgui library: imgui is build by default, but you can
# provide your own version by setting QTIMGUI_BUILD_IMGUI to OFF
option(QTIMGUI_BUILD_IMGUI "Use imgui provided as qtimgui submodule" ON)
if (QTIMGUI_BUILD_IMGUI)
    add_library(imgui
      STATIC
      ${IMGUI_SRC}
      ${IMGUI_HEAD}
    )
    target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/imgui)
endif(QTIMGUI_BUILD_IMGUI)

