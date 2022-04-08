cmake_minimum_required(VERSION 3.21)
project(vcpkg_test)

set(CMAKE_CXX_STANDARD 17)

find_package(Boost REQUIRED COMPONENTS)
include_directories(${BOOST_INCLUDE_DIR})

if(Boost_FOUND)
    MESSAGE("BOOST WAS FOUND, WOOOOOO!")
endif()

find_package(SQLite3 REQUIRED)
find_package(fmt CONFIG REQUIRED)

add_executable(vcpkg_test src/main.cpp)
target_link_libraries(vcpkg_test PRIVATE ${Boost_LIBRARIES} ${SQLite3_LIBRARIES} fmt::fmt-header-only)

if(WIN32)
    target_link_libraries(vcpkg_test PRIVATE  ws2_32)
endif()
