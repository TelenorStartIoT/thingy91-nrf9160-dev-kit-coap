# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.13.1)

list(APPEND mcuboot_OVERLAY_CONFIG
  "${CMAKE_CURRENT_SOURCE_DIR}/mcuboot_overlay-rsa.conf"
  )

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(telenor_mic_coap)

FILE(GLOB app_sources src/*.c)
target_sources(app PRIVATE ${app_sources})
zephyr_include_directories(src)
