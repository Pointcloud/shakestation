################################################################################
# Set minimum required version of cmake, project name and compile options
################################################################################
cmake_minimum_required(VERSION 2.8.3)
project(shakestation)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

################################################################################
# Find catkin packages and libraries for catkin and system dependencies
################################################################################
find_package(catkin REQUIRED COMPONENTS
  std_msgs
  geometry_msgs
  message_generation
  rospy
  robotis_controller_msgs
  manipulator_h_base_module_msgs
)


################################################################################
# Setup for python modules and scripts
################################################################################


################################################
## Declare ROS messages, services and actions ##
################################################

add_message_files(
  FILES
  JointPose.msg
  KinematicsPose.msg
)

## Generate services in the 'srv' folder
# add_service_files(
#   FILES
#   Service1.srv
#   Service2.srv
# )

## Generate actions in the 'action' folder
# add_action_files(
#   FILES
#   Action1.action
#   Action2.action
# )

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)

###################################
## catkin specific configuration ##
###################################

catkin_package(
  #INCLUDE_DIRS include
  LIBRARIES shakestation
  CATKIN_DEPENDS rospy std_msgs geometry_msgs message_runtime
  DEPENDS system_lib
)

###########
## Build ##
###########

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
)

## Declare a C++ library
# add_library(${PROJECT_NAME}
#   src/${PROJECT_NAME}/shakestation.cpp
# )


#############
## Install ##
#############

##########
## Test ##
##########


