cmake_minimum_required(VERSION 3.14)
project(ddwaf)
include(ExternalProject)

ExternalProject_Add(libddwaf
    GIT_REPOSITORY https://github.com/DataDog/libddwaf.git
    GIT_TAG 5fe5f1b065bf9e7a1b58bfae2a1dcbb9f6ba4231
    INSTALL_DIR ${CMAKE_SOURCE_DIR}
    CMAKE_ARGS
        -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE}
        -DCMAKE_MAKE_PROGRAM=${CMAKE_MAKE_PROGRAM}
        -DLIBDDWAF_BUILD_SHARED=OFF
        -DLIBDDWAF_BUILD_STATIC=ON
        -DLIBDDWAF_MSVC_RUNTIME_LIBRARY=/MD
        -DCMAKE_INSTALL_LIBDIR=lib
        -DCMAKE_INSTALL_PREFIX:PATH=<INSTALL_DIR>
)
