cmake_minimum_required(VERSION 3.5.1)
project(navtech_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    message_generation
    std_msgs
    sensor_msgs
)

add_message_files(
  FILES
    CameraConfigurationMessage.msg
    RadarBScanMsg.msg
    RadarConfigurationMsg.msg
    RadarFftDataMsg.msg
)
generate_messages(
  DEPENDENCIES
    std_msgs
    sensor_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
    std_msgs
    sensor_msgs
)
