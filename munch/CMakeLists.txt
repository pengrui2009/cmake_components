cmake_minimum_required(VERSION 3.0)
set(project munch)

set(CMAKE_PREFIX_PATH "${CMAKE_PREFIX_PATH};/home/tusen/workspace/c++/cmake_components/noms/build;/home/tusen/workspace/c++/cmake_components/noms/build/fruit/CMakeFiles/Export/lib/cmake/noms;/home/tusen/workspace/c++/cmake_components/noms/build/veg/CMakeFiles/Export/lib/cmake/noms")
# set(third_lib_dir ${CMAKE_CURRENT_SOURCE_DIR}/ext)

find_package(noms COMPONENTS fruit)

add_executable(${project} src/main.cpp)

target_include_directories(${project}
  PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:$include>
)

target_link_libraries(${project}
  PUBLIC
    noms::fruit
)

# ...
