cmake_minimum_required(VERSION 3.10.2)

project(FireEmblemGL)

add_executable(${PROJECT_NAME} main.cpp)

find_package(glfw3 3.3 REQUIRED)
find_package(OpenGL REQUIRED)

target_link_libraries(${PROJECT_NAME} glfw ${GLFW_LIBRARIES})
target_link_libraries(${PROJECT_NAME} OpenGL::GL)

add_subdirectory(dto/character)

target_link_libraries(${PROJECT_NAME} ./dto/character)

target_include_directories(${PROJECT_NAME} PRIVATE ./dto/character)