cmake_minimum_required (VERSION 3.24.0)

project(SimplTF)

# Project options
option(BUILD_STATIC "Build SimplTF statically" ON)
if (BUILD_STATIC)
	option(BUILD_SHARED_LIBS OFF)
else ()
	option(BUILD_SHARED_LIBS ON)
endif()


# 3rd party library path
set(LIBRARY_PATH ${CMAKE_SOURCE_DIR}/Deps)

# Set the local include directory for the engine
set(SIMPLTF_INCLUDE_DIR ${CMAKE_SOURCE_DIR}/include/SimplTF/)

# Set global options
set(CMAKE_CXX_STANDARD 23)

add_subdirectory("Deps")
add_subdirectory("src")
add_subdirectory("Tests")
