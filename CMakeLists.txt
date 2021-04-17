cmake_minimum_required(VERSION 3.1)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
project(Test)

add_executable(App src/main.cpp
	src/Log.cpp

)

add_custom_command(TARGET App POST_BUILD 
	COMMAND ${CMAKE_COMMAND} -E copy
	${CMAKE_SOURCE_DIR}/build/compile_commands.json
	${CMAKE_SOURCE_DIR}
	)

target_include_directories(App PRIVATE /usr/local/include/)
target_include_directories(App PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/include)
target_compile_options(App PUBLIC -Wall -Wextra -Wpedantic -Werror)

set_target_properties(App PROPERTIES RUNTIME_OUTPUT_DIRECTORY_DEBUG ${CMAKE_SOURCE_DIR}/bin/debug/ 
	RUNTIME_OUTPUT_DIRECTORY_RELEASE ${CMAKE_SOURCE_DIR}/bin/release/)


 
 
