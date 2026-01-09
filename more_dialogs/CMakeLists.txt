cmake_minimum_required(VERSION 4.1)

project(tinyfd_moredialogs C)

# library tinyfd_moredialogs

set(target tinyfd_moredialogs)
add_library(${target})
target_sources(${target} PRIVATE
    tinyfd_moredialogs.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_include_directories(${target} INTERFACE
    ${CMAKE_CURRENT_LIST_DIR}
)