set(TARGET CameraStream)
add_library(${TARGET} MODULE CameraReader.cpp )
install(TARGETS ${TARGET} DESTINATION ${CMAKE_INSTALL_PREFIX}/redpesk/${PROJECT_NAME}/lib)