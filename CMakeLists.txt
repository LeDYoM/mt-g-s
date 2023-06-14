cmake_minimum_required(VERSION 3.16)
project(
  mt-g-s
  VERSION 1.0.1
  # DESCRIPTION ""
  # [HOMEPAGE_URL <url-string>]
  LANGUAGES CXX)

set(current_target mtgs)

add_executable(${current_target})
target_sources(${current_target} PRIVATE src/main.cpp)

target_compile_features(${current_target} PUBLIC cxx_std_20)

target_compile_options(${current_target} PUBLIC
        $<$<CXX_COMPILER_ID:MSVC>:/Wall /WX>
#        $<$<CXX_COMPILER_ID:MSVC>:/W4 /WX>
        $<$<NOT:$<CXX_COMPILER_ID:MSVC>>:-Wall -Wextra -pedantic -Wno-unknown-pragmas>
    )
set(CMAKE_COMPILE_WARNING_AS_ERROR ON)
