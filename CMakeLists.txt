# minimum require
cmake_minimum_required(VERSION 3.11.0)

# global solution
project(MyCustomImgui VERSION 0.1.0)

# 设置动态库/静态库生成路径
set(LIBRARY_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/out)

set(PROJECT_DIR ${PROJECT_SOURCE_DIR})
message("PROJECT_DIR: ${PROJECT_DIR}")

set(IMGUI_DIR ${PROJECT_SOURCE_DIR}/thirdparty/imgui)
message("IMGUI_DIR: ${IMGUI_DIR}")




# goto subs
add_subdirectory(thirdparty)
add_subdirectory(examples)