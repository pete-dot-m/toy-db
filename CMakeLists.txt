cmake_minimum_required(VERSION 3.10)

if(NOT DEFINED CMAKE_C_COMPILER)
  set(CMAKE_C_COMPILER clang)
  set(CMAKE_CXX_COMPILER clang++)
endif()

project(db C)

# Set C standard
set(CMAKE_C_STANDARD 23)
set(CMAKE_C_STANDARD_REQUIRED ON)

# Set output directory
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# Add the main executable
add_executable(db src/main.c)

# Optional: Add compiler flags for warnings
if(MSVC)
    target_compile_options(db PRIVATE /W4)
else()
    target_compile_options(db PRIVATE -Wall -Wextra -Wpedantic)
endif()
