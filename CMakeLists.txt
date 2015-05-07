cmake_minimum_required(VERSION 2.8.3)
project(rail_user_queue_manager)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  message_generation
)

################################################
## Declare ROS messages, services and actions ##
################################################

## Messages
add_message_files(
  FILES
  UserStatus.msg
  Queue.msg
)

## Services
add_service_files(
  FILES
  UpdateQueue.srv
)

generate_messages()

###################################################
## Declare things to be passed to other projects ##
###################################################

## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package()

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(include
  ${catkin_INCLUDE_DIRS}
)

## Declare a cpp executable
add_executable(${PROJECT_NAME}
  src/${PROJECT_NAME}.cpp
)

## Add message build dependencies (needed for source build)
add_dependencies(${PROJECT_NAME} ${PROJECT_NAME}_gencpp)

## Specify libraries to link a library or executable target against
target_link_libraries(${PROJECT_NAME}
   ${catkin_LIBRARIES}
)

#############
## Install ##
#############

## Mark executables and/or libraries for installation
install(TARGETS ${PROJECT_NAME}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
