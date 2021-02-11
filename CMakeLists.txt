cmake_minimum_required(VERSION 3.0.2)
project(vn_ros_integration)

find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs sensor_msgs)

catkin_package(CATKIN_DEPENDS roscpp rospy std_msgs sensor_msgs)

include_directories(include/vn_ros_integration)
include_directories(${catkin_INCLUDE_DIRS})

add_executable(vn_ros_integration src/vn_node.cpp src/VNdata.cpp src/UARTcom.cpp)
add_dependencies(vn_ros_integration ${catkin_EXPORTED_TARGETS})
target_link_libraries(vn_ros_integration ${catkin_LIBRARIES})
