cmake_minimum_required(VERSION 3.5.1)
project(falcon_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    message_generation
    std_msgs
    geometry_msgs
    grid_map_msgs
    actionlib_msgs
)

add_action_files(
  FILES
    PhotoTarget.action
)
generate_messages(
  DEPENDENCIES
    std_msgs
    geometry_msgs
    grid_map_msgs
    actionlib_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
    std_msgs
    geometry_msgs
    grid_map_msgs
    actionlib_msgs
)
