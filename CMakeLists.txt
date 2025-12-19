cmake_minimum_required(VERSION 3.16.0)
project(spacenav_ros)

find_package(catkin REQUIRED COMPONENTS
  catkin_virtualenv
  geometry_msgs
  rospy
  sensor_msgs
)

catkin_package()

catkin_generate_virtualenv(
  INPUT_REQUIREMENTS requirements.in
)

install(FILES requirements.txt
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

catkin_install_python(PROGRAMS
  scripts/spacenav_node
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
