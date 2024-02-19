cmake_minimum_required(VERSION 3.28)

project("glfw-vscode-cmake-setup" LANGUAGES C)

if (APPLE)
    include_directories(/opt/homebrew/include)
    link_directories(/opt/homebrew/lib)
else()
    find_package(glfw3 3.3 REQUIRED)
endif()

find_package(OpenGL REQUIRED)

add_executable(main main.c)
target_link_libraries(main glfw OpenGL::GL)