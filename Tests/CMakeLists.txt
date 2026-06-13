cmake_minimum_required(VERSION 3.10)

project(VKRefApp VERSION 0.0.1 LANGUAGES CXX)

#Test source file
set(TEST_SRC_FILE ${CMAKE_CURRENT_SOURCE_DIR}/test.cpp)
#Validate that it exists
if (NOT EXISTS "${TEST_SRC_FILE}")
    message(FATAL_ERROR "Test source file does not exist: ${TEST_SRC_FILE}")
endif()

add_executable(VKRefApp ${TEST_SRC_FILE})

# Link exec to the top-level lib
target_link_libraries(VKRefApp PRIVATE VkReflection)