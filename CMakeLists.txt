cmake_minimum_required(VERSION 3.10)
project(CompressIt)

# Set the C standard
set(CMAKE_C_STANDARD 11)

# Include directories
include_directories(${CMAKE_SOURCE_DIR}/include)

# Source files
file(GLOB SOURCES "src/*.c")

# Create the library
add_library(CompressIt STATIC ${SOURCES})

# Build library
install(TARGETS CompressIt DESTINATION lib)
install(DIRECTORY include/ DESTINATION include)

# Examples

add_executable(main main.c)
target_link_libraries(main CompressIt)