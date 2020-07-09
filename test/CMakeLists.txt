find_package(Threads REQUIRED)
find_package(GTest REQUIRED)
find_package(GMock REQUIRED)

add_executable(OperatorTest PlusTest.cpp MinusTest.cpp)

target_include_directories(OperatorTest
    PRIVATE ${GTEST_INCLUDE_DIRS} ${GMOCK_INCLUDE_DIRS})

target_link_libraries(OperatorTest
    PRIVATE ${GTEST_LIBRARIES} GMock::GMock GMock::Main ${CMAKE_THREAD_LIBS_INIT})

target_link_libraries(OperatorTest PUBLIC plus minus)

gtest_add_tests(OperatorTest "" AUTO)
