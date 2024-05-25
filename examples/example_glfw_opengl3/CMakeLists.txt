cmake_minimum_required (VERSION 3.8.1)

# 获取当前文件夹路径
get_filename_component(CURRENT_DIR ${CMAKE_CURRENT_LIST_FILE} DIRECTORY)
 
# 获取文件夹名称
get_filename_component(FOLDER_NAME ${CURRENT_DIR} NAME)
 
# 打印文件夹名称
message("当前目录路径: ${CURRENT_DIR}")
message("当前文件夹名称: ${FOLDER_NAME}")

project(${FOLDER_NAME})
