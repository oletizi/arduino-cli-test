project(arduino-cli-test)
cmake_minimum_required(VERSION 3.20)
set (CMAKE_CXX_STANDARD 11)
# 1.57
set (TEENSY_ROOT "$ENV{HOME}/Library/Arduino15/packages/teensy/hardware/avr/1.57.2")
set (TEENSY_LIBS "$(TEENSY_ROOT)/libraries")
include_directories(
        "$(TEENSY_ROOT)/cores/teensy4"
        # This is super gross, but I can't seem to get the variables to work properly.
        "$ENV{HOME}/Library/Arduino15/packages/teensy/hardware/avr/1.57.2/libraries/SD/src"
        "$ENV{HOME}/Library/Arduino15/packages/teensy/hardware/avr/1.57.2/libraries/SPI"
        )
#target_sources(SD "/Users/orion/Library/Arduino15/packages/teensy/hardware/avr/1.57.2/libraries/SD/src/SD.h")

add_executable(arduino-cli-test loop.h loop.cpp)
#target_include_directories(arduino-cli-test PRIVATE cores/teensy4)
