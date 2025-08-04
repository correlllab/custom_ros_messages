cmake_minimum_required(VERSION 3.8)
project(custom_ros_messages)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(action_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)


rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/Dummy.msg"            # add .msg files if any
  "msg/MotorCmd.msg"
  "msg/MotorCmds.msg"
  "msg/MotorState.msg"
  "msg/MotorStates.msg"
  "srv/Query.srv"
  "srv/UpdateTrackedObject.srv"
  "srv/SetHandAngles.srv"
  "action/DualArm.action"
  "action/HandAdaptiveForce.action"
  DEPENDENCIES std_msgs sensor_msgs builtin_interfaces geometry_msgs

)

ament_package()
