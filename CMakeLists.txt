CMAKE_MINIMUM_REQUIRED(VERSION 3.0)
PROJECT(OPENGL)

# Find OPENGL
find_package(OPENGL REQUIRED)

# Find GLUT
set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH}" "${PROJECT_SOURCE_DIR}/extern/freeglut")
find_package(GLUT REQUIRED)

# Generate example
include_directories(${GLUT_INCLUDE_DIR})
add_executable(${PROJECT_NAME} src/main.cpp)
target_link_libraries(${PROJECT_NAME} ${GLUT_LIBRARIES})