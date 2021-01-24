# Robotics_ROS_RTAB-Map

Robot Simultaneous Localization and Mapping (SLAM) within a Gazebo simulated office environment utilizing 
the [ROS RTAB-MAP Package](http://wiki.ros.org/rtabmap_ros).  RTAB-Map (Real-Time Appearance-Based Mapping)
is a popular SLAM solution implemented as a ROS Packager. 

Custom ROS package:
- **my_robot**:  Simple robot consisting of 2 rotational wheels and a caster wheel for movement and a LiDAR sensor for sensing.

## Usage

Clone this project into your Catkin workspace's src directory:
```
$ cd ~/catkin_ws/src
$ git clone https://github.com/jarix/Robotics_ROS_RTAB-Map
```

Get ros-teleop package:
`$ git clone https://github.com/ros-teleop/teleop_twist_keyboard`

Build:
```
$ cd ~/catkin_ws
$ catkin_make
$ source devel/setup.bash
```

Launch the Robot World (my_robot, Gazebo, and RViz):
```
$ roslaunch my_robot world.launch
```

Launch teleop to control the robot with keyboard:
```
$ rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

Launch RTAB-Map SLAM:
```
$ roslaunch my_robot mapping.launch
```

View the created Database:
```
$ rtabmap-databaseViewer ~/catkin_ws/src/my_robot/maps/rtabmap.db
```

## Environment & Dependencies

Developed and tested on ROS Kinetic. 

## Screenshots

### Office Environment in Gazebo to be SLAMmed
![Gazebo office world](./screenshots/gazebo_world.jpg)

### Created MAP viewed in rtabmap-databaseViewer

