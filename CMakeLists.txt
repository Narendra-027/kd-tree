cmake_minimum_required(VERSION 2.8)

set(OpenCv_STATIC on)

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

#include_directories('C:/opencv/sources/include')
#include_directories('C:/opencv/build/x64/vc15/lib')

file(GLOB srcs *.cpp *.h*)

add_executable(kdtree ${srcs})
target_link_libraries(kdtree ${OpenCV_LIBS})
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)