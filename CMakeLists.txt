project(libsuspend)
cmake_minimum_required(VERSION 2.8.9)

add_library(suspend SHARED
  libsuspend.c
  sysfs.c
  autosleep.c
  earlysuspend.c
  legacy.c
  mocksuspend.c)
set_target_properties(suspend PROPERTIES VERSION 1.0.0 SOVERSION 1)
target_link_libraries(suspend -lpthread)

install(TARGETS suspend  LIBRARY DESTINATION lib)
install(FILES libsuspend.h DESTINATION include)
