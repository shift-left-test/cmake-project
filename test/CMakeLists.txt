find_package(Threads REQUIRED)
find_package(GTest REQUIRED)
find_package(GMock REQUIRED)

add_executable(SampleTest SqrtTest.cpp AbsTest.cpp)

target_include_directories(SampleTest
    PRIVATE ${GTEST_INCLUDE_DIRS} ${GMOCK_INCLUDE_DIRS})

target_link_libraries(SampleTest
    PRIVATE GTest::GTest GMock::GMock GMock::Main ${CMAKE_THREAD_LIBS_INIT})

target_link_libraries(SampleTest PUBLIC sqrt abs)

gtest_add_tests(SampleTest "" AUTO)
