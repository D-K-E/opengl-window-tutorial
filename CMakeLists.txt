cmake_minimum_required (VERSION 2.8.3)
project("Hello Window OpenGL")

find_package(OpenGL REQUIRED)

include_directories(
    # my headers
    "./include/"
    )

#set( GLFW_STATIC_LIB "/media/kaan/Data7510/GitProjects/glfw-build/src/libglfw3.a")
set( GLFW_SHARED_LIB
    "${PROJECT_SOURCE_DIR}/libs/glfw/src/libglfw.so")

set ( ALL_LIBS 
    ${OpenGL}
    ${GLFW_SHARED_LIB}
    "-ldl"
    )

add_executable(myWin 
    "src/glad.c"
    "src/window.cpp"
    )
target_link_libraries(myWin ${ALL_LIBS})
install(TARGETS myWin DESTINATION "${PROJECT_SOURCE_DIR}/bin/")
