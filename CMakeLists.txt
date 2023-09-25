cmake_minimum_required(VERSION 3.8)
project(ros2neuro_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_srvs REQUIRED)

# ---- generate msgs and srvs
rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/NeuroDataFloat.msg"
  "msg/NeuroDataInt32.msg"
  "msg/NeuroDataInfo.msg"
  "msg/NeuroHeader.msg"
  "msg/NeuroFrame.msg"
  "msg/NeuroEvent.msg"
  "msg/NeuroDecoder.msg"
  "msg/NeuroOutput.msg"
  "srv/GetAcquisitionInfo.srv"
  DEPENDENCIES std_msgs std_srvs
)

ament_export_dependencies(rosidl_default_runtime)


ament_package()







