cmake_minimum_required (VERSION 3.6)

project (camera-demo CXX)
find_package(PkgConfig REQUIRED)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON) 

set(AFM_APP_DIR ${CMAKE_INSTALL_PREFIX}/redpesk CACHE PATH "Root application directory")
set(APPDIR ${AFM_APP_DIR}/${PROJECT_NAME})

pkg_check_modules (AFBBINDING REQUIRED afb-binding)
include_directories(${AFBBINDING_INCLUDE_DIRS})
link_libraries(${AFBBINDING_LDFLAGS})

add_subdirectory(CameraStream)
add_subdirectory(ObjectDetection)
add_subdirectory(test/afb-test)

configure_file(in.main-manifest.yml manifest.yml @ONLY)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/manifest.yml DESTINATION ${APPDIR}/.rpconfig)
