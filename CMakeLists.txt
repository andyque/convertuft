cmake_minimum_required(VERSION 2.8)

project (convertutf)

set(SRC
./ConvertUTF.c
./ConvertUTFWrapper.cpp
)

include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}
)

add_library(convertutf STATIC
  ${SRC}
)

INSTALL(
  TARGETS convertutf
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  COMPONENT library
)

INSTALL(FILES ConvertUTF.h
        DESTINATION "include"
)
