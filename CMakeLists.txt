cmake_minimum_required(VERSION 3.5)

project(clone)

add_subdirectory(vendor/glfw)

add_executable(${PROJECT_NAME}
    ${CMAKE_HOME_DIRECTORY}/src/main.c
    ${CMAKE_HOME_DIRECTORY}/src/stb.c
    ${CMAKE_HOME_DIRECTORY}/src/block/block.c
    ${CMAKE_HOME_DIRECTORY}/src/block/grass.c
    ${CMAKE_HOME_DIRECTORY}/src/block/stone.c
    ${CMAKE_HOME_DIRECTORY}/src/gfx/renderer.c
    ${CMAKE_HOME_DIRECTORY}/src/gfx/shader.c
    ${CMAKE_HOME_DIRECTORY}/src/gfx/texture.c
    ${CMAKE_HOME_DIRECTORY}/src/gfx/vao.c
    ${CMAKE_HOME_DIRECTORY}/src/gfx/vbo.c
    ${CMAKE_HOME_DIRECTORY}/src/gfx/window.c
    ${CMAKE_HOME_DIRECTORY}/src/util/camera.c
    ${CMAKE_HOME_DIRECTORY}/src/util/mat.c
    ${CMAKE_HOME_DIRECTORY}/src/util/vec.c
    ${CMAKE_HOME_DIRECTORY}/src/world/chunk.c
    ${CMAKE_HOME_DIRECTORY}/src/world/noise.c
    ${CMAKE_HOME_DIRECTORY}/src/world/world.c
    ${CMAKE_HOME_DIRECTORY}/vendor/glad/src/glad.c
)

target_include_directories(${PROJECT_NAME} PRIVATE vendor/glad/include vendor/stb/)
target_link_libraries(${PROJECT_NAME} PRIVATE glfw)
