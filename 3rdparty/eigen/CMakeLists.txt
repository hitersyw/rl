cmake_minimum_required(VERSION 2.8.11)

project(eigen)

include(ExternalProject)

ExternalProject_Add(
	eigen
	#GIT_REPOSITORY https://gitlab.com/libeigen/eigen.git
	#GIT_TAG 3.3.7
	URL https://gitlab.com/libeigen/eigen/-/archive/3.3.7/eigen-3.3.7.tar.gz
	#URL ${CMAKE_CURRENT_SOURCE_DIR}/eigen-3.3.7.tar.gz
	URL_MD5 9e30f67e8531477de4117506fe44669b
	CMAKE_ARGS -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE} -DCMAKE_CFG_INTDIR=${CMAKE_CFG_INTDIR} -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX} -DCMAKE_PREFIX_PATH=${CMAKE_PREFIX_PATH} -DCMAKE_TRY_COMPILE_CONFIGURATION=${CMAKE_TRY_COMPILE_CONFIGURATION} -DBUILD_TESTING=OFF -DEIGEN_TEST_NOQT=ON
	INSTALL_DIR ${CMAKE_INSTALL_PREFIX}
)
