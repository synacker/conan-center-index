cmake_minimum_required(VERSION 3.15)
project(PackageTest LANGUAGES C)

find_package(PkgConfig REQUIRED)
pkg_check_modules(CAP REQUIRED IMPORTED_TARGET libcap)

add_executable(example example.c)
target_link_libraries(example PRIVATE PkgConfig::CAP)
