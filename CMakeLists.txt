cmake_minimum_required( VERSION 2.8 )
project(direct_method)

set(CMAKE_BUILD_TYPE "Debug")
set(CMAKE_CXX_FLAGS "-std=c++11 -O3" )

include_directories( "/usr/include/eigen3" )

find_package( OpenCV 3.1 REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )

find_package( Sophus REQUIRED )
include_directories( ${Sophus_INCLUDE_DIRS} )

find_package(Pangolin REQUIRED )
include_directories( ${Pangolin_INCLUDE_DIRS} )

add_executable( direct_method direct_method.cpp)
target_link_libraries( direct_method ${OpenCV_LIBS} ${Sophus_LIBRARIES} ${Pangolin_LIBRARIES} )
