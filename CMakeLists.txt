cmake_minimum_required (VERSION 3.13)

project (CameraDemo CXX)
find_package(PkgConfig REQUIRED)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON) 

include(${CMAKE_CURRENT_SOURCE_DIR}/conf.d/cmake/config.cmake)

#add_compile_options( -fPIC) 
pkg_check_modules (AFBBINDING REQUIRED afb-binding)
#pkg_check_modules(HELPERS REQUIRED afb-libhelpers)

include_directories(${AFBBINDING_INCLUDE_DIRS})
link_libraries(${AFBBINDING_LDFLAGS})

add_subdirectory(CameraStream)
add_subdirectory(ObjectDetection)
#add_subdirectory(DisplayApp)

