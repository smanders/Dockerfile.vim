cmake_minimum_required(VERSION 3.31)
if(NOT DEFINED CMAKE_INSTALL_PREFIX)
  # NOTE: CMAKE_INSTALL_PREFIX must be set before project() to take effect
  set(CMAKE_INSTALL_PREFIX ${CMAKE_BINARY_DIR}/dist CACHE PATH "Install path prefix, prepended onto install directories.")
endif()
project(Dockerfile.vim VERSION 21.09.06.2) # date-of-master-branch-commit.revision
set(_dirs ftdetect ftplugin indent snippets syntax)
install(DIRECTORY ${_dirs} DESTINATION .)
set(CPACK_GENERATOR RPM)
set(CPACK_RPM_PACKAGE_ARCHITECTURE "noarch")
set(CPACK_PACKAGING_INSTALL_PREFIX "/usr/share/vim/vimfiles")
set(CPACK_PACKAGE_FILE_NAME ${PROJECT_NAME}-v${PROJECT_VERSION})
include(CPack)
