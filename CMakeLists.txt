project(kdelibs)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")

cmake_minimum_required(VERSION 2.8)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_INCLUDE_DIRECTORIES_PROJECT_BEFORE ON)

include(MacroLibrary)
include(FindQt4)
include(FindKDE4Internal)
include(ConfigureChecks)

configure_file(config.h.cmake ${CMAKE_CURRENT_BINARY_DIR}/config.h)
configure_file(kdecore/kdefakes.h.cmake ${CMAKE_CURRENT_BINARY_DIR}/kdecore/kdefakes.h)

include_directories(${CMAKE_SOURCE_DIR} ${CMAKE_BINARY_DIR} ${CMAKE_SOURCE_DIR}/interfaces)
include_directories( ${CMAKE_CURRENT_SOURCE_DIR}
                     ${CMAKE_CURRENT_BINARY_DIR}
                     ${QT_INCLUDE_DIR}
                     ${QT_QTCORE_INCLUDE_DIR} )

add_subdirectory(solid)