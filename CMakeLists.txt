project(multipart-parser-c)

cmake_minimum_required(VERSION 2.8.11)

add_definitions(-std=c89 -ansi -pedantic)

if(${CMAKE_BUILD_TYPE} STREQUAL "Debug")
  add_definitions(-DDEBUG_MULTIPART)
endif()

set(LIB multipart-parser-c)
set(SRC multipart_parser.c)
set(INC multipart_parser.h)

add_library(${LIB} STATIC ${SRC})

install(TARGETS ${LIB} ARCHIVE DESTINATION lib) 
install(FILES ${INC} DESTINATION include)

