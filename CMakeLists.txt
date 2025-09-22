# The following lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.5)

set(COMPONENTS main)
include($ENV{IDF_PATH}/tools/cmake/project.cmake)
project(camera_example)
# idf_build_set_property(COMPILE_OPTIONS -D__INT32_TYPE__=int -D__UINT32_TYPE__="unsigned int" APPEND)
# target_compile_options(main PRIVATE -Wno-error)
set_target_properties(${COMPONENT_LIB} PROPERTIES COMPILE_FLAGS -Wno-error)
