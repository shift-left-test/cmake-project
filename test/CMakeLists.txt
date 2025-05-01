if(ENABLE_TEST)
  include(GoogleTest)

  add_executable(OperatorTest PlusTest.cpp MinusTest.cpp)

  if(WITH_DEFECT_CODE)
    target_sources(OperatorTest PRIVATE SegFaultTest.cpp)
  endif()

  target_link_libraries(OperatorTest PRIVATE plus minus)
  target_link_libraries(OperatorTest PRIVATE gtest gtest_main)

  gtest_add_tests(OperatorTest "" AUTO)
endif(ENABLE_TEST)
