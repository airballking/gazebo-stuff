cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
project(Plugins)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_EXPORT_COMPILE_COMMANDS 1)

find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

add_library(ButterFactoryPlugin SHARED ButterFactoryPlugin.cc)
target_link_libraries(ButterFactoryPlugin ${GAZEBO_LIBRARIES})

add_library(SwingPlugin SHARED SwingPlugin.cc)
target_link_libraries(SwingPlugin ${GAZEBO_LIBRARIES})

add_library(StickyPlugin SHARED StickyPlugin.cc)
target_link_libraries(StickyPlugin ${GAZEBO_LIBRARIES})