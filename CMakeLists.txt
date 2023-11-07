cmake_minimum_required(VERSION 3.26)
project(LicenseDetector)

set(CMAKE_CXX_STANDARD 17)
set(ENV{OPENCV_DIR} "/opt/homebrew/opt/opencv/")
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/")

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(LicenseDetector main.cpp
)

set(OpenCV_LIBS opencv_core opencv_imgproc opencv_highgui opencv_imgcodecs opencv_objdetect)

target_link_libraries(LicenseDetector ${OpenCV_LIBS})
