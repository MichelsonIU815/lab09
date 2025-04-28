cmake_minimum_required(VERSION 3.14)

include("cmake/HunterGate.cmake")
set(HUNTER_ROOT "~/hunter_download/hunter-0.23.314")
include("cmake/HunterGate.cmake")
HunterGate(
    URL "file:///home/michel/hunter_download/v0.23.314.tar.gz"
    SHA1 "572541b3a9e2c1ccb0c0e552f6dc12219c0d6a0b"
)

project(print)

option(BUILD_TESTS "Build tests" OFF)

hunter_add_package(GTest)
find_package(GTest REQUIRED)

add_library(print STATIC src/print.cpp)
target_include_directories(print PUBLIC include)

if(BUILD_TESTS)
    enable_testing()
    add_executable(check tests/test.cpp)
    target_link_libraries(check print GTest::GTest GTest::Main)
    add_test(NAME check COMMAND check)
endif()

add_executable(demo demo/main.cpp)
target_link_libraries(demo print)
install(TARGETS demo RUNTIME DESTINATION bin)
set(CPACK_PACKAGE_NAME "print")
set(CPACK_PACKAGE_VERSION "0.1.0.0")
set(CPACK_PACKAGE_VENDOR "YourName")
include(CPack)
