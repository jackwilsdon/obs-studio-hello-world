cmake_minimum_required(VERSION 2.8.12)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/../cmake/Modules/")

include(ObsPluginHelpers)

project(hello-world)

find_package(Libobs REQUIRED)

set(hello-world_SOURCES
	hello-world.c)

add_library(hello-world MODULE
	${hello-world_SOURCES})

target_link_libraries(hello-world
	libobs)

install_external_plugin_data(hello-world data)
