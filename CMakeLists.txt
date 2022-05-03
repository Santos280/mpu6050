cmake_minimum_required(VERSION 3.19)

# Pull in SDK (must be before project)
include(pico_sdk_import.cmake)

project(mpu6050)

pico_sdk_init()

add_executable(mpu6050
src/main.c
src/mpu6050.c)

target_include_directories(mpu6050 PUBLIC inc/) 


pico_enable_stdio_usb(mpu6050 1)
pico_enable_stdio_uart(mpu6050 0)

pico_add_extra_outputs(mpu6050)

target_link_libraries(mpu6050 pico_stdlib hardware_gpio hardware_i2c)
