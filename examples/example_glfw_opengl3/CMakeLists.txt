cmake_minimum_required (VERSION 3.8.1)

# 获取当前文件夹路径
get_filename_component(CURRENT_DIR ${CMAKE_CURRENT_LIST_FILE} DIRECTORY)
 
# 获取文件夹名称
get_filename_component(FOLDER_NAME ${CURRENT_DIR} NAME)
 
# 打印文件夹名称
message("当前目录路径: ${CURRENT_DIR}")
message("当前文件夹名称: ${FOLDER_NAME}")

project(${FOLDER_NAME})


file(GLOB IMGUI_SRC ${IMGUI_DIR}/*.cpp)
file(GLOB IMGUI_HEAD ${IMGUI_DIR}/*.h)

file(GLOB IMGUI_IMPL_OPENGL3_SRC ${IMGUI_DIR}/backends/imgui_impl_opengl3*.cpp)
file(GLOB IMGUI_IMPL_OPENGL3_HEAD ${IMGUI_DIR}/backends/imgui_impl_opengl3*.h)

file(GLOB IMGUI_IMPL_GLFW_SRC ${IMGUI_DIR}/backends/imgui_impl_glfw*.cpp)
file(GLOB IMGUI_IMPL_GLFW_HEAD ${IMGUI_DIR}/backends/imgui_impl_glfw*.h)



include_directories(${IMGUI_DIR}/)
include_directories(${IMGUI_DIR}/backends/)
include_directories(${IMGUI_DIR}/examples/libs/glfw/include/)

set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /NODEFAULTLIB:MSVCRT.lib")
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /NODEFAULTLIB:legacy_stdio_definitions.lib")

# 包含静态库路径
link_directories(${IMGUI_DIR}/examples/libs/glfw/lib-vc2010-64/)
# 链接静态库
link_libraries(opengl32 glfw3 imgui)



add_executable(${FOLDER_NAME} ${IMGUI_DIR}/examples/example_glfw_opengl3/main.cpp  
      #${IMGUI_SRC}
      #${IMGUI_HEAD} 
      ${IMGUI_IMPL_OPENGL3_SRC}
      ${IMGUI_IMPL_OPENGL3_HEAD} 
      ${IMGUI_IMPL_GLFW_SRC} 
      ${IMGUI_IMPL_GLFW_HEAD})
