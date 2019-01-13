cmake_minimum_required(VERSION 3.9)
#add_definitions(-DOS_MACOSX)
project(echo)

add_definitions(-DOS_LINUX)

include_directories("${PROJECT_SOURCE_DIR}")
set(CMAKE_CXX_STANDARD 11)

aux_source_directory(handy HANDY_SRCS)
add_library(handy
        ${HANDY_SRCS})

add_executable(codec-cli
        examples/codec-cli.cc)
target_link_libraries(codec-cli handy pthread)

add_executable(codec-svr
        examples/codec-svr.cc)
target_link_libraries(codec-svr handy pthread)

add_executable(daemon
        examples/daemon.cc)
target_link_libraries(daemon handy pthread)

add_executable(echo
        examples/echo.cc)
target_link_libraries(echo handy pthread)

add_executable(hsha
        examples/hsha.cc)
target_link_libraries(hsha handy pthread)

add_executable(http-hello
        examples/http-hello.cc)
target_link_libraries(http-hello handy pthread)

add_executable(idle-close
        examples/idle-close.cc)
target_link_libraries(idle-close handy pthread)

add_executable(reconnect
        examples/reconnect.cc)
target_link_libraries(reconnect handy pthread)

add_executable(safe-close
        examples/safe-close.cc)
target_link_libraries(safe-close handy pthread)

add_executable(stat
        examples/stat.cc)
target_link_libraries(stat handy pthread)

add_executable(timer
        examples/timer.cc)
target_link_libraries(timer handy pthread)

add_executable(udp-cli
        examples/udp-cli.cc)
target_link_libraries(udp-cli handy pthread)

add_executable(udp-hsha
        examples/udp-hsha.cc)
target_link_libraries(udp-hsha handy pthread)

add_executable(udp-svr
        examples/udp-svr.cc)
target_link_libraries(udp-svr handy pthread)

add_executable(write-on-empty
        examples/write-on-empty.cc)
target_link_libraries(write-on-empty handy pthread)

add_executable(10m-cli
        10m/10m-cli.cc)
target_link_libraries(10m-cli handy pthread)

add_executable(10m-svr
        10m/10m-svr.cc)
target_link_libraries(10m-svr handy pthread)

#add_executable(kqueue
#        raw-examples/kqueue.cc)
#target_link_libraries(kqueue handy)

