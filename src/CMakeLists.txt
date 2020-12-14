cmake_minimum_required(VERSION 3.16)
project(customocd C ASM)

set(CMAKE_VERBOSE_MAKEFILE 1)

set(CMAKE_C_STANDARD 99)

set(CMAKE_C_FLAGS "\
        -DHAVE_CONFIG_H \
        -DRELSTR=\\\"aa\\\" \
        -DGITVERSION=\\\"bb\\\" \
        -DF_CPU=48000000  \
")

include_directories(..)
include_directories(.)
include_directories(./helper)
include_directories(../jimtcl)

add_executable(customocd
        main.c
        openocd.c)