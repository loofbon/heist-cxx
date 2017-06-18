cmake_minimum_required (VERSION 3.1)
project (heist)
include_directories ("${PROJECT_SOURCE_DIR}")
set (CMAKE_CXX_STANDARD 11)
add_library(heist heist/light_ptr.cpp heist/lock_pool.cpp heist/pooled_locker.cpp heist/set.cpp)

enable_testing()
find_package(GTest REQUIRED)

add_executable(heist-tests heist-tests/list.cpp)
target_link_libraries(heist GTest::GTest GTest::Main)

add_test(ListTest heist-tests)
