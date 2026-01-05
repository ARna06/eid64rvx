cmake_minimum_required(VERSION 3.10)

project(umbra)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(CMAKE_CXX_STANDARD 23)

file(GLOB_RECURSE SRC_FILES src/*.cpp)

add_library(umbra ${SRC_FILES})

target_include_directories(umbra
  PUBLIC includes
)

# target_compile_options(umbra PUBLIC -fsanitize=address)
# target_link_options(umbra PUBLIC -fsanitize=address)

if (UMBRA_BUILD_EXAMPLES)
  add_subdirectory(examples)
endif()