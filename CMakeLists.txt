project(clm)
cmake_minimum_required(VERSION 2.8)

find_package( OpenCV REQUIRED )



find_package(OpenMP)
if (OPENMP_FOUND)
    set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
    set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
endif()

file(GLOB SOURCES "source/CLM_Lib/*.cpp" "source/*.cpp" "source/QuadProg++/*.cc" "source/tinyxml/*.cpp")

include_directories(${CMAKE_SOURCE_DIR}/source)
#include_directories(${CMAKE_SOURCE_DIR}/source/CLM_Lib)
#include_directories(${CMAKE_SOURCE_DIR}/QuadProg++)
#include_directories(${CMAKE_SOURCE_DIR}/tinyxml)

add_executable(clm ${SOURCES})
target_link_libraries( clm ${OpenCV_LIBS} )

