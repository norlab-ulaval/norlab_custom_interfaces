cmake_minimum_required(VERSION 3.5.1)
project(any_msgs)

find_package(catkin REQUIRED
  COMPONENTS
    message_generation
    sensor_msgs
    std_msgs
)

add_message_files(
  FILES
    BoolStamped.msg
    Event.msg
    State.msg
    UserInteractionOption.msg
    ExtendedJointState.msg
    Float64Stamped.msg
    ImuWithTrigger.msg
    PointContact.msg
    SensorTimeInfo.msg
)
add_service_files(
  FILES
    ProcessFile.srv
    SetFloat32.srv
    SetFloat64.srv
    SetPose.srv
    SetTopic.srv
    SetUInt32.srv
    Toggle.srv
    UserInteraction.srv
    Shutdown.srv
    SetString.srv
    GetPose.srv
    GetString.srv
    GetStrings.srv
    GetUInt8.srv
)
generate_messages(
  DEPENDENCIES
    sensor_msgs
    std_msgs
)

catkin_package(
  CATKIN_DEPENDS
    message_runtime
    sensor_msgs
    std_msgs
)
