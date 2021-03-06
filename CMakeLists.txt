cmake_minimum_required(VERSION 3.3)
project(SDL2)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${SDL2_SOURCE_DIR}/cmake")


set(SOURCE_FILES source/src/main.cpp source/src/graphics.cpp source/headers/graphics.h source/src/game.cpp source/headers/game.h source/headers/input.h source/src/input.cpp source/src/sprite.cpp source/headers/sprite.h source/headers/globals.h)
add_executable(SDL2 ${SOURCE_FILES})

find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

include_directories(${SDL2_INCLUDE_DIR}
        ${SDL2_IMAGE_INCLUDE_DIR}
        ${SDL2_TTF_INCLUDE_DIR})


target_link_libraries(SDL2 ${SDL2_LIBRARY}
        ${SDL2_IMAGE_LIBRARIES}
        ${SDL2_TTF_LIBRARIES})
