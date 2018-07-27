cmake_minimum_required(VERSION 2.8)

SET(CMAKE_VERBOSE_MAKEFILE  ON)
SET(CMAKE_COLOR_MAKEFILE ON)
SET(CMAKE_WARN_DEPRECATED ON)
SET(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project (fbcp CXX C)

SET(COMPILE_DEFINITIONS -Werror)

add_executable(fbcp main.c)

target_link_libraries(fbcp
  bcm_host
  vchostif
  )

INSTALL(TARGETS fbcp
  RUNTIME DESTINATION "/usr/bin"
  )
