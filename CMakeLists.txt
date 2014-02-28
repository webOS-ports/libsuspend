project(libsuspend)
cmake_minimum_required(VERSION 2.8.9)

set(CMAKE_C_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS "-Wall")
set(CMAKE_C_FLAGS_DEBUG "-O0 -ggdb -g")
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -ggdb -g")
set(CMAKE_C_FLAGS_RELEASE "-O3")
set(CMAKE_CXX_FLAGS_RELEASE "-O3")
set(CMAKE_C_FLAGS "-Wall -Werror -Wextra")

find_package(Threads REQUIRED)

add_library(suspend SHARED
  libsuspend.c
  sysfs.c
  autosleep.c
  earlysuspend.c
  legacy.c
  mocksuspend.c)

install(TARGETS suspend  LIBRARY DESTINATION lib)
