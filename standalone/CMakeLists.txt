cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project(
  BoilerplateStandalone
  LANGUAGES CXX
)

# Add any dependencies.

add_subdirectory(${CMAKE_CURRENT_LIST_DIR}/.. _deps/Boilerplate)

# Create a standalone executable.

file(GLOB sources CONFIGURE_DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp)

add_executable(BoilerplateStandalone ${sources})

set_target_properties(BoilerplateStandalone PROPERTIES CXX_STANDARD 17 OUTPUT_NAME "Boilerplate")

target_link_libraries(BoilerplateStandalone Boilerplate)