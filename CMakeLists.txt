cmake_minimum_required(VERSION 3.14)

project(CppProjectTemplate VERSION 1.0.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Include directories
include_directories(${PROJECT_SOURCE_DIR}/include)

# Collect source files
file(GLOB_RECURSE SOURCES 
    "${PROJECT_SOURCE_DIR}/main.cc"
    "${PROJECT_SOURCE_DIR}/src/*.cc"
)

# Create executable
if(SOURCES)
    add_executable(${PROJECT_NAME} ${SOURCES})
    
    # Link directories if needed
    target_include_directories(${PROJECT_NAME} PRIVATE 
        ${PROJECT_SOURCE_DIR}/include
    )
endif()

# Enable testing
enable_testing()
