project(clm)
cmake_minimum_required(VERSION 2.8)

find_package( OpenCV REQUIRED )



find_package(OpenMP)
if (OPENMP_FOUND)
    set (CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
    set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
endif()

file(GLOB SOURCES "CLM_Lib/*.cpp" "*.cpp" "QuadProg++/*.cc" "tinyxml/*.cpp"
                  "CLM_Lib/*.h" "*.h" "QuadProg++/*.h" "tinyxml/*.h")

include_directories(${CMAKE_SOURCE_DIR})
include_directories(${CMAKE_SOURCE_DIR}/CLM_Lib)
include_directories(${CMAKE_SOURCE_DIR}/QuadProg++)
include_directories(${CMAKE_SOURCE_DIR}/tinyxml)

add_executable(clm ${SOURCES})
target_link_libraries( clm ${OpenCV_LIBS} )

