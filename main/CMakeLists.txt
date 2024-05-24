cmake_minimum_required(VERSION 3.29.3)
project(_3DGameProject VERSION 1.0.0.0)

configure_file(MainConfig.h.in MainConfig.h)

add_executable(main WIN32 main.cpp)

add_library(freeglut ./OpenGL/freeglut-3.4.0/src/)
add_subdirectory(freeglut)
target_link_libraries(main PUBLIC freeglut)

target_include_directories(main PUBLIC "${PROJECT_BINARY_DIR}")