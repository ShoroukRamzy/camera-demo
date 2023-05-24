set(TARGET ObjectDetection)
add_library(${TARGET} MODULE ObjectDetection.cpp )

#add_library(ObjectDetection MODULE ObjectDetection.cpp )
install(TARGETS ${TARGET} DESTINATION ${CMAKE_INSTALL_PREFIX}/redpesk/${PROJECT_NAME}/lib)