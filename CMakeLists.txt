project(SkiaDemo)
cmake_minimum_required(VERSION 3.0)

# Set C++ standard. The SDK containers currently have CMake 3.0.2 which
# does not support target property CXX_STANDARD and friends. So just pass
# it as compile option.
add_compile_options(-std=c++11)

find_package(PkgConfig)
find_package(PNG REQUIRED)
find_library(LIBPTHREAD pthread)
if (NOT LIBPTHREAD)
	message(FATAL_ERROR "Can't find libpthread")
endif()

add_subdirectory(ext)
add_subdirectory(src)
