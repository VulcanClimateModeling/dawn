##===------------------------------------------------------------------------------*- CMake -*-===##
##                          _
##                         | |
##                       __| | __ ___      ___ ___
##                      / _` |/ _` \ \ /\ / / '_  |
##                     | (_| | (_| |\ V  V /| | | |
##                      \__,_|\__,_| \_/\_/ |_| |_| - Compiler Toolchain
##
##
##  This file is distributed under the MIT License (MIT).
##  See LICENSE.txt for details.
##
##===------------------------------------------------------------------------------------------===##
include(GoogleTest)

set(executable ${PROJECT_NAME}CUnittest)
add_executable(${executable}
  TestOptions.cpp
  TestCompiler.cpp
)

target_add_dawn_standard_props(${executable})
target_link_libraries(${executable} DawnC DawnUnittest gtest gtest_main)
gtest_discover_tests(${executable} TEST_PREFIX "DawnC::Unit::" DISCOVERY_TIMEOUT 30)
