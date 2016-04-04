cmake_minimum_required(VERSION 2.8.3)
project(ardrone)

find_package(catkin REQUIRED COMPONENTS rospy message_generation std_msgs std_srvs geometry_msgs sensor_msgs)

add_message_files(FILES Navdata.msg)
add_service_files(FILES SetCam.srv)
generate_messages()

catkin_package(CATKIN_DEPENDS rospy message_runtime std_msgs std_srvs geometry_msgs sensor_msgs)

catkin_install_python(PROGRAMS node/ardrone DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(DIRECTORY msg/ DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/msg)
install(DIRECTORY srv/ DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/srv)
