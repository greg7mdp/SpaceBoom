cmake_minimum_required(VERSION 3.24)

project(tests)

set( CMAKE_CXX_STANDARD 20 )
set( CMAKE_CXX_EXTENSIONS OFF )
set( CXX_STANDARD_REQUIRED ON)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

if(NOT MSVC)
   add_compile_options("$<$<COMPILE_LANGUAGE:CXX>:-pedantic;-Wall;-Wextra;-Wcast-qual;-Wdisabled-optimization;-Winit-self;-Wmissing-include-dirs;-Wswitch-default;-Wno-unused>")
   if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
      add_compile_options("$<$<COMPILE_LANGUAGE:CXX>:-Wlogical-op;-Wstrict-null-sentinel>")
   endif()
else()
   add_compile_options("$<$<COMPILE_LANGUAGE:CXX>:/W4;/Zc:__cplusplus>")
endif()

add_subdirectory(OpenGL)

