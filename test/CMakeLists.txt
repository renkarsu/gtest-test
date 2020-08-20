cmake_minimum_required(VERSION 3.17.3)

FetchContent_MakeAvailable(googletest)

add_subdirectory(${googletest_SOURCE_DIR} ${googletest_BINARY_DIR})


add_executable(sample1_unittest sample1_unittest.cc)

target_link_libraries(sample1_unittest sample1 gtest_main)

# C++11をオプションに加える
target_compile_features(sample1_unittest PUBLIC cxx_std_11)

gtest_add_tests(TARGET sample1_unittest)
