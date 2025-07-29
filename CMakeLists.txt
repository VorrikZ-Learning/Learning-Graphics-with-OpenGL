cmake_minimum_required(VERSION 3.10)
project(OpenGLTriangle)

set(CMAKE_C_STANDARD 23)
set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include paths for GLAD and GLFW headers
include_directories(
    ${CMAKE_SOURCE_DIR}/KHR
    ${CMAKE_SOURCE_DIR}/external
)

# Link directories for precompiled GLFW libs
link_directories(${CMAKE_SOURCE_DIR}/external/lib-vc2022)

# Source files
set(SOURCES
    main.cpp
    external/glad.c
)

# Add executable
add_executable(OpenGLTriangle ${SOURCES})

# Link GLFW and OpenGL
target_link_libraries(OpenGLTriangle
    glfw3
    opengl32
)
