cmake_minimum_required (VERSION 3.1)
project (heist)
include_directories ("${PROJECT_SOURCE_DIR}")
set (CMAKE_CXX_STANDARD 11)
add_library(heist heist/light_ptr.cpp heist/lock_pool.cpp heist/pooled_locker.cpp heist/set.cpp)

find_package(GTest)
if (GTEST_FOUND)
  enable_testing()
  include_directories ("${GTEST_INCLUDE_DIRS}")

  add_executable(heist-tests tests/list.test.cpp)
  target_link_libraries(heist-tests heist GTest::GTest GTest::Main)

  add_test(ListTest heist-tests)
endif (GTEST_FOUND)
