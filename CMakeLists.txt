cmake_minimum_required(VERSION 3.10)

project(opengl-boilerplate)

# opengl handling
find_package(OpenGL REQUIRED)

# error handling
if(P_BINARY_DIR STREQUAL P_SOURCE_DIR)
  message (FATAL_ERROR "Please select another Build Directory!")
endif()
if(P_SOURCE_DIR MATCHES " ")
  message("Your Source Directory contains white spaces. This can cause compiler errors.")
endif()

# Library paths
set(GLFW_SOURCE_DIR "external/glfw")
set(GLAD_SOURCE_DIR "external/glad")

# Library: GLFW
# disable documentation, tests and examples of glfw
set(BUILD_SHARED_LIBS OFF CACHE BOOL "")
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "")
set(GLFW_BUILD_TESTS OFF CACHE BOOL "")
set(GLFW_BUILD_DOCS OFF CACHE BOOL "")
set(GLFW_INSTALL OFF CACHE BOOL "")
add_subdirectory(${GLFW_SOURCE_DIR})

# Library: GLAD
add_subdirectory(${GLAD_SOURCE_DIR})

include_directories(
  ${GLFW_SOURCE_DIR}/includes
  ${GLFW_SOURCE_DIR}/deps
)

# Search source files
file(GLOB SOURCE
  "src/*.cpp"
)

# Add source files
add_executable(opengl-boilerplate
  ${SOURCE}
)

# link libraries
target_link_libraries(
  opengl-boilerplate
  glad
  glfw
)
