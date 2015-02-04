cmake_minimum_required(VERSION 2.8)

project (convertutf)

SET_SOURCE_FILES_PROPERTIES(./ConvertUTF.c PROPERTIES LANGUAGE CXX )
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-exceptions -std=c++11 -Wno-deprecated-declarations -Wno-reorder")

if(IOS OR MACOX)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -stdlib=libc++")
endif()

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
