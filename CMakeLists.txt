cmake_minimum_required(VERSION 3.5)
project(gtec_msgs)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

set(msg_files
  "msg/GenericRanging.msg"
  "msg/Ranging.msg"
  "msg/UWBRanging.msg"
  "msg/DWRanging.msg"
  "msg/PozyxRanging.msg"
  "msg/RangingDiff.msg"
  "msg/PozyxRangingWithCir.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
)
