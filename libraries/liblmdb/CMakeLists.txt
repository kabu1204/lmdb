cmake_minimum_required(VERSION 2.8)
project(lmdb)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

add_library(lmdb SHARED 
    mdb.c
    midl.c
)

target_compile_definitions(lmdb PUBLIC MDB_DEBUG)

add_executable(mtest mtest.c)
target_link_libraries(mtest PRIVATE lmdb)
