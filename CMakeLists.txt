cmake_minimum_required(VERSION 2.8)

project( DisplayImage )

set(CMAKE_SYSTEM_NAME Linux)
include(CMakeForceCompiler)
CMAKE_FORCE_C_COMPILER(arm-linux-gnueabihf-gcc GNU)
CMAKE_FORCE_CXX_COMPILER(arm-linux-gnueabihf-g++ GNU)

#set(OpenCV_DIR "/root/opencv-x86_64/opencv/build")
#set(OpenCV_DIR "/root/opencv-arm/opencv/platforms/linux/build_hardfp")

set(OpenCV_DIR "/opencv/build")
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake-modules)
#set(OpenCV_STATIC ON)
find_package( OpenCV REQUIRED)

include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable( DisplayImage main.cpp )

#set(CMAKE_EXE_LINKER_FLAGS "-static")
target_link_libraries( DisplayImage ${OpenCV_LIBS} )
