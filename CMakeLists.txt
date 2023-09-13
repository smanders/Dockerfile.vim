cmake_minimum_required(VERSION 3.24)
if(NOT DEFINED CMAKE_INSTALL_PREFIX)
  # NOTE: CMAKE_INSTALL_PREFIX must be set before project() to take effect
  set(CMAKE_INSTALL_PREFIX ~/.vim CACHE PATH "Install path prefix, prepended onto install directories.")
endif()
project(Dockerfile.vim VERSION 21.09.06) # date of master branch commit
set(_dirs ftdetect ftplugin indent snippets syntax)
install(DIRECTORY ${_dirs} DESTINATION .)
set(CPACK_GENERATOR TXZ)
set(CPACK_INCLUDE_TOPLEVEL_DIRECTORY OFF)
set(CPACK_PACKAGE_FILE_NAME ${PROJECT_NAME}-${PROJECT_VERSION})
include(CPack)
