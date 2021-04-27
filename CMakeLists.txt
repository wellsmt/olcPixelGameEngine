cmake_minimum_required(VERSION 3.6)
project(game)

set(CMAKE_CXX_STANDARD 14)  # for c++11

find_package(X11 REQUIRED)
link_libraries(${X11_LIBRARIES})
include_directories(${X11_INCLUDE_DIR})

find_package(PNG REQUIRED)
include_directories(${PNG_INCLUDE_DIR})
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)
include_directories( ${OPENGL_INCLUDE_DIRS}  ${GLUT_INCLUDE_DIRS} )

add_executable(game olcExampleProgram.cpp)
target_link_libraries(game ${PNG_LIBRARY})
target_link_libraries(game ${OPENGL_LIBRARIES} ${GLUT_LIBRARY} )


