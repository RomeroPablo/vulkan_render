cmake_minimum_required(VERSION 3.30)

project(game VERSION 1.0)


set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)
find_package(SDL2 REQUIRED)
find_package(Vulkan REQUIRED)

add_definitions(-DSDL_VIDEO_VULKAN=1)

add_executable(game src/main.cpp)

target_link_libraries(game glfw OpenGL::GL SDL2::SDL2 Vulkan::Vulkan)

target_include_directories(game PUBLIC ${PROJECT_SOURCE_DIR}/include)
