cmake_minimum_required(VERSION 3.15)
project(test_openiap C)

find_package(openiap REQUIRED)

add_executable(test_openiap test_openiap.c)
target_link_libraries(test_openiap PRIVATE openiap::openiap)
