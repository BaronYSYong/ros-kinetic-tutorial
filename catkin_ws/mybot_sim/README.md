# Building a Simulated Model for Gazebo and ROS from Scratch

## Reference
* Github
    * https://github.com/richardw05/mybot_ws.git
* Overview
    * http://moorerobots.com/blog
* Part 1: Simulating Robot Models for ROS
    * http://moorerobots.com/blog/post/1
* Part 2: Simulating Sensors in Gazebo
    * http://moorerobots.com/blog/post/2
* Part 3: Simulating the ROS Navigation Stack
    * http://moorerobots.com/blog/post/3

## Environment
* Ubuntu 16.04 Xenial
* ROS Kinetic

## Run the models
```
$ git clone -b base https://github.com/richardw05/mybot_ws.git
$ cd mybot_ws
$ catkin build
$ echo "source ~/github/mybot_ws/devel/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
$ roslaunch mybot_gazebo mybot_world.launch
```
In another terminal
```
$ rostopic pub /cmd_vel geometry_msgs/Twis"linear:
  x: 0.2
  y: 0.0
  z: 0.0
angular:
  x: 0.0
  y: 0.0
  z: 0.1"
```
Another terminal
```
$ roslaunch mybot_description mybot_rviz.launch
```
Change the setting of rviz to
Fixed Frame: odom
Add RobotModel

## Misc
* If the Gazebo plugin cannot be found, install the ros kinetic controllers
```
$ sudo apt-get install ros-kinetic-ros-control
$ sudo apt-get install ros-kinetic-ros-controllers
$ sudo apt-get install ros-kinetic-gazebo-msgs
$ sudo apt-get install ros-kinetic-gazebo-ros
```
*If robot is not moving in rviz, check the tf transformation tree
```
* rosrun tf view_frames
* evince frames.pdf
```
