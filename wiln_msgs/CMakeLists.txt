cmake_minimum_required(VERSION 3.5.1)
project(wiln_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    message_generation
)

add_service_files(
  FILES
    LoadMapTraj.srv
    PlayLoop.srv
    SaveMapTraj.srv
)
generate_messages(
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
)
