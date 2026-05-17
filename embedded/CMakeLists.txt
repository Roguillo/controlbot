cmake_minimum_required(VERSION 3.28)

include(pico_sdk_import.cmake)

project(embedded LANGUAGES C CXX ASM)

pico_sdk_init()

add_executable(${PROJECT_NAME}
    main.c
)

target_link_libraries(${PROJECT_NAME}
    pico_stdlib
    pico_cyw43_arch_none
    pico_time
)

pico_enable_stdio_usb(${PROJECT_NAME} 1)
pico_enable_stdio_uart(${PROJECT_NAME} 0)

pico_add_extra_outputs(${PROJECT_NAME})
