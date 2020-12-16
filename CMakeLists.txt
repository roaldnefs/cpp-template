cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

project(
  Boilerplate
  VERSION 1.0
  LANGUAGES CXX
)

# Include guards to make sure the project isn't build from a source directory
if(PROJECT_SOURCE_DIR STREQUAL PROJECT_BINARY_DIR)
  message(
    FATAL_ERROR
      "In-source build not allowed. Please make a new directory (called a build directory) and run CMake from there."
  )
endif()

# Add the source files, but keep in mind the globbing sources is considered bad
# practice as CMake's generators may not detect new file automatically. You can
# always explicitly mention new files.
file(GLOB_RECURSE headers CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/include/*.h")
file(GLOB_RECURSE sources CONFIGURE_DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/source/*.cpp")

# Create the library, for header-only libraries change all PUBLIC flags to
# INTERFACE and create an interface target:
#   add_library(Boilerplate INTERFACE)
#   set_target_properties(Greeter PROPERTIES INTERFACE_COMPILE_FEATURES
#   cxx_std_17)

add_library(Boilerplate ${headers} ${sources})

set_target_properties(Boilerplate PROPERTIES CXX_STANDARD 17)

# Link any dependencies (if required), example:
#    target_link_libraries(Boilerplate PUBLIC cxxopts)

target_include_directories(
  Boilerplate PUBLIC $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include/${PROJECT_NAME}-${PROJECT_VERSION}>
)