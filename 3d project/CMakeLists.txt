cmake_minimum_required(VERSION 3.10)
project(My3DApp)

set(CMAKE_CXX_STANDARD 11)

find_package(OpenGL REQUIRED)
find_package(glfw3 3.3 REQUIRED)
add_subdirectory(deps/glad)

include_directories(src deps/glad/include)

add_executable(My3DApp src/main.cpp src/shader.cpp src/model.cpp src/camera.cpp)
target_link_libraries(My3DApp OpenGL::GL glfw glad)
