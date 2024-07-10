cmake_minimum_required(VERSION 3.13)  # CMake version check
project(CFG_HPP)               # Create project "simple_example"
set(CMAKE_CXX_STANDARD 26)            # Enable c++14 standard\

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

include_directories(${CMAKE_SOURCE_DIR}/include)

# Add executable target with source files listed in SOURCE_FILES variable
add_executable(CFG_HPP bin/src/extensionInstall.cpp)

find_package(CURL REQUIRED)
target_link_libraries(CFG_HPP PRIVATE CURL::libcurl)

find_package(SFML COMPONENTS system window graphics CONFIG REQUIRED)
target_link_libraries(CFG_HPP PRIVATE sfml-system sfml-network sfml-graphics sfml-window)

find_package(7zip CONFIG REQUIRED)
target_link_libraries(CFG_HPP PRIVATE 7zip::7zip)