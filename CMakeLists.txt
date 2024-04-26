################################################################################
# Set minimum required version of cmake, project name and compile options
################################################################################
cmake_minimum_required(VERSION 2.8.3)
project(uoa_poc3_msgs)

################################################################################
# Find catkin packages and libraries for catkin and system dependencies
################################################################################
find_package(catkin REQUIRED COMPONENTS
  message_generation
  geometry_msgs #この行を追加 0718
)

################################################################################
# Setup for python modules and scripts
################################################################################

################################################################################
# Declare ROS messages, services and actions
################################################################################
add_message_files(
  FILES
# ①ロボットへの移動指示   
   r_navi_command.msg
   r_costmap.msg
# ②ロボットの情報通知
   r_info.msg  
   r_size.msg
   r_corner.msg
# ③移動指示受信結果 
   r_navi_result.msg 
# ④ロボットへの緊急停止
   r_emergency_command.msg
# ⑤緊急停止受信結果
   r_emergency_result.msg
# ⑥ロボットの状態報告
   r_state.msg
   r_pose.msg
   r_pose_optional.msg
   r_angle.msg
   r_angle_optional.msg
   r_battery.msg
   r_current_optional.msg
)

generate_messages(
  DEPENDENCIES
  geometry_msgs #この行を追加 0718
)

################################################################################
# Declare ROS dynamic reconfigure parameters
################################################################################

################################################################################
# Declare catkin specific configuration to be passed to dependent projects
################################################################################
catkin_package(
  CATKIN_DEPENDS message_runtime geometry_msgs
)

################################################################################
# Build
################################################################################

################################################################################
# Install
################################################################################

################################################################################
# Test
################################################################################
