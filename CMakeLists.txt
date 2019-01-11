cmake_minimum_required(VERSION 3.5)
project(tinydir_vendor)

include(ExternalProject)
ExternalProject_Add(tinydir-1.2.4
  PREFIX tinydir-1.2.4
  URL https://github.com/cxong/tinydir/archive/1.2.4.tar.gz
  URL_MD5 15978c5f498e2ff3d26a9975c734cda0
  CMAKE_ARGS
    -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
  BUILD_IN_SOURCE 1
  PATCH_COMMAND
    ${CMAKE_COMMAND} -E copy "${CMAKE_CURRENT_SOURCE_DIR}/tinydir_cmakelists.txt" <SOURCE_DIR>/CMakeLists.txt
)

configure_file(tinydir_vendorConfig.cmake.in "${PROJECT_BINARY_DIR}/tinydir_vendorConfig.cmake" @ONLY)
configure_file(tinydir_vendorConfig-version.cmake.in "${PROJECT_BINARY_DIR}/tinydir_vendorConfig-version.cmake" @ONLY)

install(FILES
  "${PROJECT_BINARY_DIR}/tinydir_vendorConfig.cmake"
  "${PROJECT_BINARY_DIR}/tinydir_vendorConfig-version.cmake"
  DESTINATION share/${PROJECT_NAME}/cmake)
