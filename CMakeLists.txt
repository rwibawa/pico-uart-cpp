# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/ryan/workspace_arm/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(pico-uart-cpp C CXX ASM)

set(PICO_CXX_ENABLE_EXCEPTIONS 1)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(pico-uart-cpp pico-uart-cpp.cpp )

pico_set_program_name(pico-uart-cpp "pico-uart-cpp")
pico_set_program_version(pico-uart-cpp "0.1")
pico_set_program_description(foo "this is a foo")
pico_set_program_url(foo "https://github.com/rwibawa/pico-uart-cpp")

pico_enable_stdio_uart(pico-uart-cpp 1)
pico_enable_stdio_usb(pico-uart-cpp 0)

# Add the standard library to the build
target_link_libraries(pico-uart-cpp pico_stdlib)

# Add any user requested libraries
target_link_libraries(pico-uart-cpp
        hardware_timer
        hardware_clocks
        )

pico_add_extra_outputs(pico-uart-cpp)

