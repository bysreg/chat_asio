cmake_minimum_required(VERSION 2.8)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(Boost COMPONENTS system thread REQUIRED)

include_directories(
	${Boost_INCLUDE_DIRS}
	${PROJECT_SOURCE_DIR}
)

add_executable(client client.cpp)
add_executable(server server.cpp)
target_link_libraries(client ${Boost_LIBRARIES})
target_link_libraries(server ${Boost_LIBRARIES})
