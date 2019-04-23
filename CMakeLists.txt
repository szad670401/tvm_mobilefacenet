cmake_minimum_required(VERSION 3.6)
project(tvm_mobilefacenet)


#SET(CMAKE_C_COMPILER  /Users/yujinke/work/chainer-nnvm/external_r24/android-toolchain-arm64/bin/aarch64-linux-android-gcc)
#SET(CMAKE_CXX_COMPILER /Users/yujinke/work/chainer-nnvm/external_r24/android-toolchain-arm64/bin/aarch64-linux-android-g++)


set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -ldl -lpthread")
SET(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
SET(CMAKE_LIBRARY_OUTPUT_DIRECTORY  ${CMAKE_CURRENT_SOURCE_DIR})
SET(HOME_TVM /Users/yujinke/downloads/tvm-0.5)
find_package(OPENCV REQUIRED)

INCLUDE_DIRECTORIES(${OpenCV_INCLUDE_DIRS})
INCLUDE_DIRECTORIES(${HOME_TVM}/include)
INCLUDE_DIRECTORIES(${HOME_TVM}/3rdparty/dmlc-core/include)
INCLUDE_DIRECTORIES(${HOME_TVM}/3rdparty/dlpack/include)
add_executable(tvm_mobilefacenet  tvm_runtime_pack.cc main.cpp)
target_link_libraries(tvm_mobilefacenet    ${OpenCV_LIBS})


