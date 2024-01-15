cmake_minimum_required(VERSION 3.27)
project(PacMan_SI)


set(CMAKE_CXX_STANDARD 17)

set(GLFW_LIBRARY_DIR "${PROJECT_SOURCE_DIR}/dependencies/glfw/lib-vc2022")
set(GLEW_LIBRARY_DIR "${PROJECT_SOURCE_DIR}/dependencies/glew/library")
set(GLFW_INCLUDE_DIR "${PROJECT_SOURCE_DIR}/dependencies/glfw/include")
set(GLEW_INCLUDE_DIR "${PROJECT_SOURCE_DIR}/dependencies/glew/include")


link_directories(${GLFW_LIBRARY_DIR} ${GLEW_LIBRARY_DIR})

add_executable(PacMan_SI main.cpp)

add_custom_command(TARGET PacMan_SI POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy
        "${GLEW_LIBRARY_DIR}/glew32.dll"
        $<TARGET_FILE_DIR:PacMan_SI>
)

include_directories(${GLFW_INCLUDE_DIR} ${GLEW_INCLUDE_DIR})

target_link_libraries(PacMan_SI PRIVATE glfw3.lib glew32.lib opengl32.lib)

