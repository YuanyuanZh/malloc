cmake_minimum_required(VERSION 3.2)
project(malloc)

set(MODULE_NAME malloc)
set(SOURCE morecore.c bitset.c)
add_library(${MODULE_NAME} ${SOURCE})
target_link_libraries(${MODULE_NAME} cunit)
set_target_properties(${MODULE_NAME} PROPERTIES
		COMPILE_FLAGS "-mpopcnt")
#set_target_properties(${MODULE_NAME} PROPERTIES
#COMPILE_FLAGS "-mpopcnt -mlzcnt")
ADD_TEST_TARGET(bitset_basic_tests ${MODULE_NAME})