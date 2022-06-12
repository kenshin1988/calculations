cmake_minimum_required(VERSION 3.02.8)

set(calcname calc)

enable_language(ASM)

set(CALC_INC "${CMAKE_CURRENT_SOURCE_DIR}/inc")

set(calc_sources
    "${CMAKE_CURRENT_SOURCE_DIR}/src/calc.c"
)

include_directories(
    ${CALC_INC}
)

add_library(${calcname} ${calc_sources})

target_link_libraries(${calcname} calc)
target_include_directories(${calcname} PUBLIC "$<BUILD_INTERFACE:${CALC_INC}>")