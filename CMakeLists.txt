cmake_minimum_required(VERSION 4.1)

project(demo C)

# fetch tinyfiledialogs library

include(FetchContent)
FetchContent_Declare(
    tinyfiledialogs
    GIT_REPOSITORY https://github.com/hghpublic/vareille-tinyfiledialogs.git
    GIT_TAG dev/0
)
FetchContent_MakeAvailable(tinyfiledialogs)

# demo executable

set(target hello)
add_executable(${target})
target_sources(${target} PRIVATE
    ${target}.c
)
target_compile_features(${target} PRIVATE c_std_23)
target_link_libraries(${target} PRIVATE tinyfiledialogs)
