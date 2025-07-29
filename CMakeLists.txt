cmake_minimum_required(VERSION 3.13)

set(CMAKE_TOOLCHAIN_FILE "$ENV{VCPKG_ROOT}/scripts/buildsystems/vcpkg.cmake")

set(TGT logcabin)

project(${TGT} VERSION 1.0.0)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_CXX_STANDARD 17)
SET(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory("Client")
add_subdirectory("Protocol")
add_subdirectory("Core")
add_subdirectory("Event")
add_subdirectory("RPC")
add_subdirectory("Server")
add_subdirectory("Storage")
add_subdirectory("Tree")
