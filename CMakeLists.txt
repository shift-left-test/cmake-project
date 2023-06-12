# MIT License
#
# Copyright (c) 2020 LG Electronics, Inc.
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.

cmake_minimum_required(VERSION 3.3 FATAL_ERROR)

project(cmake-project VERSION 1.0.0)

include(CMakeUtils)

set_cxx_standard(14)
set_default_build_type(Release)

option(ENABLE_STATIC_ANALYSIS "Enable static analysis checks" ON)
option(ENABLE_TEST "Enable testing" OFF)
option(WITH_DEFECT_CODE "With defect code" OFF)

if(ENABLE_STATIC_ANALYSIS)
  enable_static_analysis(cppcheck cpplint)
endif()

if(ENABLE_TEST)
  enable_testing()
  enable_test_coverage()
endif()

add_subdirectory(minus)
add_subdirectory(plus)
add_subdirectory(program)

if(ENABLE_TEST)
add_subdirectory(test)
endif()
