

cmake_minimum_required(VERSION 3.13)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(PICO_BOARD pico_w CACHE STRING "Board type")

include(pico_sdk_import.cmake)
project(Interrupt C CXX ASM)
pico_sdk_init()
add_executable(Interrupt Interrupt.c )
pico_set_program_name(Interrupt "Interrupt")
target_link_libraries(Interrupt pico_stdlib)
pico_add_extra_outputs(Interrupt)

# Modify the below lines to enable/disable output over UART/USB
pico_enable_stdio_uart(Interrupt 1)
pico_enable_stdio_usb(Interrupt 1)

