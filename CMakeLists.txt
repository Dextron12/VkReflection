cmake_minimum_required(VERSION 3.10)

# Project name & version
project(VkReflection VERSION 1.0.0 LANGUAGES CXX)

#CXX Standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Collect project sources (Need to explicitly include them in the future, GLOB_RECURSE is unreliable especially on Windows)
file(GLOB_RECURSE VKREF_SRC CONFIGURE_DEPENDS src/*.cpp)
file(GLOB_RECURSE VKREF_INC CONFIGURE_DEPENDS include/*.hpp)

# Options
option(TEST_Exec "Build VkReflection with the included test application" ON)

# Find system packages
#find_package()

# Create library
add_library(VkReflection STATIC ${VKREF_SRC})

# Link library
target_link_libraries(VkReflection STATIC ${VKREF_SRC} PUBLIC)

# Test application
if (TEST_Exec)
    add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/Tests)
    message(STATUS "Compiling test application")
endif()
