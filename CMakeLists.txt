

cmake_minimum_required (VERSION 3.0.0)

project(vacestory)


# INCLUDE(FindPkgConfig)

find_package(sdl2)

# PKG_SEARCH_MODULE(SDL2 REQUIRED sdl2)
# PKG_SEARCH_MODULE(SDL2IMAGE REQUIRED SDL2_image>=2.0.0)

SET(SDL_INCLUDE_DIRS "/usr/local/Cellar/sdl2/2.0.4/lib")
SET(SDL2IMAGE_LIBRARIES "/usr/local/Cellar/sdl2_image/2.0.1_1/lib/libSDL2_image.dylib")

INCLUDE_DIRECTORIES(${SDL_INCLUDE_DIRS} ${SDL2IMAGE_INCLUDE_DIRS})

set(TARGET main)

include_directories(source/headers)

aux_source_directory(source/src SOURCE)

MESSAGE(STATUS "SOURCE: ${SOURCE}")

add_executable(main ${SOURCE})

MESSAGE(STATUS ${SDL2IMAGE_LIBRARIES})

TARGET_LINK_LIBRARIES(${TARGET} "SDL2" ${SDL2IMAGE_LIBRARIES})
