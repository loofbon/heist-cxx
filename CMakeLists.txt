cmake_minimum_required (VERSION 2.6)
project (heist)
include_directories ("${PROJECT_SOURCE_DIR}")
add_library(heist heist/light_ptr.cpp heist/lock_pool.cpp heist/pooled_locker.cpp heist/set.cpp)
