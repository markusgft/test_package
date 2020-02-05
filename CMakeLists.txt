cmake_minimum_required(VERSION 2.8.3)
project(test_package)

find_package(catkin REQUIRED COMPONENTS
  ct_optcon
)

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wfatal-errors -std=c++14")

catkin_package(
  CATKIN_DEPENDS ct_optcon
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(testLqr src/LQR.cpp)
target_link_libraries(testLqr ${catkin_LIBRARIES})
