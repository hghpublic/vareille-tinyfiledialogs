cmake_minimum_required(VERSION 4.1)

project(tinyfiledialogs
    LANGUAGES C
    VERSION 3.21.2
    DESCRIPTION "tiny file dialogs ( cross-platform C C++ )"
    HOMEPAGE_URL "http://tinyfiledialogs.sourceforge.net"
)

# library tinyfiledialogs

set(target tinyfiledialogs)
add_library(${target})
target_sources(${target} PRIVATE
    tinyfiledialogs.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_include_directories(${target} INTERFACE
    ${CMAKE_CURRENT_LIST_DIR}
)

if(PROJECT_IS_TOP_LEVEL)
# executable hello

set(target hello)
add_executable(${target})
target_sources(${target} PRIVATE
    ${target}.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE tinyfiledialogs)

if(CMAKE_HOST_SYSTEM_NAME STREQUAL "Windows")
# executable hello_wchar_t

set(target hello_wchar_t)
add_executable(${target})
target_sources(${target} PRIVATE
    ${target}.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE tinyfiledialogs)
endif(CMAKE_HOST_SYSTEM_NAME STREQUAL "Windows")

endif(PROJECT_IS_TOP_LEVEL)




# library tinyfd_moredialogs
add_subdirectory(more_dialogs)

