cmake_minimum_required(VERSION 3.2)

add_library(libL1 STATIC ipOket.cpp ipOket.h)
set_target_properties(libL1 PROPERTIES CXX_STANDARD 14 CXX_STANDARD_REQUIRED ON)
target_include_directories(libL1 PRIVATE ${CMAKE_BINARY_DIR})

if(MSVC)
	target_compile_options(libL1 PRIVATE /W4)
else()
	target_compile_options(libL1 PRIVATE -Wall -Wextra -Werror)
endif()
