cmake_minimum_required(VERSION 3.5.1)
project(controller_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    message_generation
    std_msgs
    nav_msgs
    actionlib_msgs
)

add_message_files(
  FILES
    FollowerOptions.msg
)
add_service_files(
  FILES
    ExportData.srv
)
add_action_files(
  FILES
    FollowPath.action
)
generate_messages(
  DEPENDENCIES
    std_msgs
    nav_msgs
    actionlib_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
    std_msgs
    nav_msgs
    actionlib_msgs
)
