cmake_minimum_required(VERSION 2.8.3)

# Set CMP0048 policy to NEW to manage version variables
cmake_policy(SET CMP0048 NEW)

project(daly_bms_msgs)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS actionlib_msgs std_msgs message_generation)


#######################################
## Declare ROS messages and services ##
#######################################

## Generate messages in the 'msg' folder
add_message_files(DIRECTORY msg
    FILES
    BalancingStatus.msg
    CellVoltageRange.msg
    CompleteStatus.msg
    MosfetStatus.msg
    Soc.msg
    State.msg
    Status.msg
    TemperatureRange.msg
)

## Generate services in the 'srv' folder
#add_service_files(
#    DIRECTORY srv
#    FILES
#)

#add_action_files(
#    FILES
#    SetElevator.action
#)


## Generate added messages and services with any dependencies listed here
generate_messages(
DEPENDENCIES
   actionlib_msgs
   std_msgs  # Or other packages containing msgs
)

catkin_package(CATKIN_DEPENDS
  actionlib_msgs
  message_runtime
  std_msgs
)
