# check cmake version
cmake_minimum_required(VERSION 3.10)
# set c++ version
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Project name
project(Project)

# Add include directories
include_directories(${CMAKE_SOURCE_DIR}/include 
		    ${CMAKE_SOURCE_DIR}/lib)

# Add source files
file(GLOB_RECURSE SOURCE_FILES ${CMAKE_SOURCE_DIR}/src/*.c)
	
# Add header files
file(GLOB_RECURSE HEADER_FILES ${CMAKE_SOURCE_DIR}/src/*.h)

# Define the executable
add_executable(${PROJECT_NAME} ${HEADER_FILES} ${SOURCE_FILES})

# Link target directories and libraries
link_directories(${CMAKE_SOURCE_DIR}/lib)
target_link_libraries(${PROJECT_NAME} libraries)
