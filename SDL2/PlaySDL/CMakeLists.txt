cmake_minimum_required(VERSION 3.10)
project(PlaySDL)

set(CMAKE_CXX_STANDARD 11)
set(SDL_DIR /usr/local/Cellar/sdl2/2.0.14_1)
set(SDL_DIR_LIB ${SDL_DIR}/lib/)
include_directories(${SDL_DIR}/include/)
link_libraries(${SDL_DIR}/lib/)


add_library(SDL2
        SHARED
        IMPORTED)
set_target_properties(SDL2
        PROPERTIES IMPORTED_LOCATION
        ${SDL_DIR_LIB}/libSDL2.dylib)

add_executable(PlaySDL main.cpp)

target_link_libraries(PlaySDL SDL2)