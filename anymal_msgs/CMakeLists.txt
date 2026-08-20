cmake_minimum_required(VERSION 3.16.3)
project(anymal_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    any_msgs
    geometry_msgs
    message_generation
    sensor_msgs
    std_msgs
)

add_message_files(
  FILES
    AnymalState.msg
    BMSState.msg
    Contact.msg
    Contacts.msg
    GaitPattern.msg
    GaitPatterns.msg
    LegAttributes.msg
    StringStamped.msg
)
add_service_files(
  FILES
    GetActiveController.srv
    GetAvailableControllers.srv
    SetBaseHeight.srv
    SetBasePose.srv
    SetBoolean.srv
    SwitchController.srv
)
generate_messages(
  DEPENDENCIES
    any_msgs
    geometry_msgs
    sensor_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    any_msgs
    geometry_msgs
    message_runtime
    sensor_msgs
    std_msgs
)
