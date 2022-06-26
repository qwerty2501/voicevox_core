cmake_minimum_required(VERSION 3.16)
project(OpenjtalkSys)

include(FetchContent)
FetchContent_Declare(
  openjtalk
  GIT_REPOSITORY https://github.com/VOICEVOX/open_jtalk.git
  GIT_TAG 1.11
  SOURCE_SUBDIR src)
FetchContent_MakeAvailable(openjtalk)

add_library(OpenjtalkSys src/openjtalk.cpp)

target_link_libraries(OpenjtalkSys PUBLIC openjtalk)

install(
  TARGETS openjtalk
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION lib)
