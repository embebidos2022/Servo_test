# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "C:/Users/santi/OneDrive/Documentos/Pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(Servo_test C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(Servo_test Servo_test.c )

pico_set_program_name(Servo_test "Servo_test")
pico_set_program_version(Servo_test "0.1")

pico_enable_stdio_uart(Servo_test 0)
pico_enable_stdio_usb(Servo_test 1)

# Add the standard library to the build
target_link_libraries(Servo_test 
                    pico_stdlib
                    hardware_pwm
                    hardware_clocks
                    hardware_adc)

pico_add_extra_outputs(Servo_test)

