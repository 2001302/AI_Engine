cmake_minimum_required(VERSION 3.30)
project(UnitTest)

#set vcpkg path
set(CMAKE_PREFIX_PATH "${CMAKE_SOURCE_DIR}/../vcpkg/vcpkg_installed/x64-windows")

add_executable (UnitTest
        test.h
        test.cpp)

# set include path
target_include_directories(UnitTest PUBLIC
        ${CMAKE_SOURCE_DIR}/vcpkg/vcpkg_installed/x64-windows/include/gtest
)
# library link
target_link_directories(UnitTest PRIVATE
        ${CMAKE_SOURCE_DIR}/vcpkg/vcpkg_installed/x64-windows/lib
)

# library name
target_link_libraries(UnitTest PRIVATE gtest)
