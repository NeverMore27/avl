cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)

include(cmake/HunterGate.cmake)

HunterGate(
    URL "https://github.com/NeverMore27/hunter/archive/v0.19.137.11.tar.gz"
    SHA1 "7c3fc568a2c3ef87632766e4995a80c8b699385d"
)

project(demo)
hunter_add_package(avl_tree)
find_package(avl_tree)

add_executable(demo ${CMAKE_CURRENT_SOURCE_DIR}/sources/demo.cpp)
target_link_libraries(demo avl_tree)
install(TARGETS demo RUNTIME DESTINATION bin)
