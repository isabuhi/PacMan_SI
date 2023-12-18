cmake_minimum_required(VERSION 3.27)
project(PacMan_SI)


set(CMAKE_CXX_STANDARD 17)

set(GLFW_LIBRARY_DIR "${PROJECT_SOURCE_DIR}/dependencies/glfw/lib-vc2022")
set(GLFW_INCLUDE_DIR "${PROJECT_SOURCE_DIR}/dependencies/glfw/include")


link_directories(${GLFW_LIBRARY_DIR})

add_executable(PacMan_SI main.cpp)

include_directories(${GLFW_INCLUDE_DIR})

target_link_libraries(PacMan_SI PRIVATE ${PROJECT_SOURCE_DIR}/dependencies/glfw/lib-vc2022/glfw3.lib opengl32.lib)

