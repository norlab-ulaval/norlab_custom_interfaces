cmake_minimum_required(VERSION 3.8)
project(norlab_custom_interfaces)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()
set(CMAKE_BUILD_TYPE "Release")

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/EncoderState.msg"
  "msg/FollowerOptions.msg"
  "msg/MotorState.msg"
  "msg/BatteryLog.msg"
  "srv/LoadMapTraj.srv"
  "srv/PlayLoop.srv"
  "srv/SaveMapTraj.srv"
  "srv/ExportData.srv"
  "action/FollowPath.action"
  DEPENDENCIES std_msgs geometry_msgs nav_msgs
)

include_directories(
  ${norlab_custom_interfaces_INCLUDE_DIRS}
)

ament_package()
