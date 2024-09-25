# Gazebo ROS Demos

* Author: Dave Coleman <davetcoleman@gmail.com>
* License: GNU General Public License, version 3 (GPL-3.0)

Example robots and code for interfacing Gazebo with ROS

## Tutorials

[ROS URDF](http://gazebosim.org/tutorials/?tut=ros_urdf)  NOT FOUND!(ROC 20240912)

## Quick Start

Rviz:

    roslaunch rrbot_description rrbot_rviz.launch


Gazebo:

    roslaunch rrbot_gazebo rrbot_world.launch
or,
    roslaunch rrbot_gazebo rrbot_world_linebyline.launch
# if you want see the structure of the launch file, please use:

ROS Control(not necessary, have been included in rrbot_world.launch):

    roslaunch rrbot_control rrbot_control.launch




Example of Moving Joints:

    rostopic pub /rrbot/joint1_position_controller/command std_msgs/Float64 "data:  1.0"
    rostopic pub /rrbot/joint2_position_controller/command std_msgs/Float64 "data: -0.9"
    
# Please note that the imputs here are the control target, not the actual joint position
# If you want to know the actual joint position, please use:

rostopic echo /rrbot/joint1_position_controller/state  
# see the live command
<!-- header: 
  seq: 167384
  stamp: 
    secs: 1674
    nsecs: 632000000
  frame_id: ''
set_point: 4.5397
process_value: 4.373938301545397
process_value_dot: -4.43111103432072e-14
error: 0.16576169845460242
time_step: 0.001
command: 16.576169845460242
p: 100.0
i: 0.01
d: 10.0
i_clamp: 0.0
antiwindup: False -->




rostopic echo /rrbot/joint_states 
# see the live position, velocity, effort
<!-- header: 
  seq: 83808
  stamp: 
    secs: 1676
    nsecs: 691000000
  frame_id: ''
name: 
  - joint1
  - joint2
position: [4.373938301545397, -0.04096546190677586]
velocity: [-4.4479642177585033e-14, 1.3653944640375512e-13]
effort: [16.576169845460242, 4.096538407510408] -->






    

## Install

Please install the necessary packages:

    sudo apt-get install ros-noetic-ros-control
    
    sudo apt-get install ros-noetic-ros-controllers


## Develop and Contribute

We welcome any contributions to this repo and encourage you to fork the project then send pull requests back to this parent repo. Thanks for your help!
 