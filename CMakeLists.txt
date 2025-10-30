cmake_minimum_required(VERSION 3.16)
project(ptz_tracker_interfaces)

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
  "action/TrackTarget.action"
)
unset( CATKIN_INSTALL_INTO_PREFIX_ROOT )
unset( CATKIN_SYMLINK_INSTALL )

ament_export_dependencies(rosidl_default_runtime)
ament_package()
