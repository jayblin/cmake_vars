cmake_minimum_required(VERSION 3.23)

project(cmake_vars VERSION 1.0.0 LANGUAGES CXX C)

add_library(cmake_vars INTERFACE)

target_include_directories(
	cmake_vars
	INTERFACE
	$<BUILD_INTERFACE:${CMAKE_CURRENT_BINARY_DIR}/include>
	$<INSTALL_INTERFACE:include>
)

configure_file(
	include/cmake_vars/config.h.in
	${CMAKE_BINARY_DIR}/include/cmake_vars/config.h
)
