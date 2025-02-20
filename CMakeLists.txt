cmake_minimum_required(VERSION 3.31.4)

project(csEigen3)

if(NOT EXISTS eigen-3.4.0)
	if(LINUX)
		file(DOWNLOAD https://gitlab.com/libeigen/eigen/-/archive/3.4.0/eigen-3.4.0.zip eigen-3.4.0.tar.gz)
		file(ARCHIVE_EXTRACT INPUT ${CMAKE_CURRENT_LIST_DIR}/eigen-3.4.0.tar.gz DESTINATION ${CMAKE_CURRENT_LIST_DIR}/)
		file(REMOVE eigen-3.4.0.tar.gz)
	elseif(WIN32)
		file(DOWNLOAD https://gitlab.com/libeigen/eigen/-/archive/3.4.0/eigen-3.4.0.zip eigen-3.4.0.zip)
		file(ARCHIVE_EXTRACT INPUT ${CMAKE_CURRENT_LIST_DIR}/eigen-3.4.0.zip DESTINATION ${CMAKE_CURRENT_LIST_DIR}/)
		file(REMOVE eigen-3.4.0.zip)
	endif()
endif()

add_subdirectory(eigen-3.4.0)
