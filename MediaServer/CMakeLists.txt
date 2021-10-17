project(cpggatewayserver)

cmake_minimum_required(VERSION 3.10.0)
 
 
FILE(GLOB_RECURSE SOURCES "*.cpp" "*.hpp" "*.ipp" "*.cc")
 

add_executable(${PROJECT_NAME} ${SOURCES})
add_dependencies(${PROJECT_NAME} Shared)

set(ALL_LIB  pthread
		libShared.a
		libboost_system.a
		libboost_filesystem.a
		pthread
		libcrypto.a
		libprotobuf-lite.a
		curl 
		libprotobuf.a 
		czmq hiredis zmq 
		libssl.a
		dl
		sqlite3
	)


target_link_libraries(${PROJECT_NAME} ${ALL_LIB})






