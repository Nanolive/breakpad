cmake_minimum_required(VERSION 3.10)

project(breakpad)

include_directories(../..)
add_definitions(-DUNICODE)

set(handler_src
handler/exception_handler.cc
)

add_library(exception_handler STATIC ${handler_src})

set(client_src
crash_generation/crash_generation_client.cc
)

add_library(crash_generation_client STATIC ${client_src})

set(common_src
../../common/windows/guid_string.cc
../../common/windows/http_upload.cc
../../common/windows/string_utils.cc
)

add_library(common STATIC ${common_src})
