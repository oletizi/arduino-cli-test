project(arduino-cli-test)
cmake_minimum_required(VERSION 3.20)
include(FetchContent)
# 1.57
#include_directories("/Library/Arduino15/packages/teensy/hardware/avr/1.57.2/libraries/SD/src")
#target_sources(SD "/Users/orion/Library/Arduino15/packages/teensy/hardware/avr/1.57.2/libraries/SD/src/SD.h")

add_executable(arduino-cli-test loop.h loop.cpp cores/teensy4/main.cpp)
target_include_directories(arduino-cli-test PRIVATE cores/teensy4)

add_executable(cores cores/teensy4/main.cpp)
target_include_directories(cores PUBLIC cores/teensy4)
