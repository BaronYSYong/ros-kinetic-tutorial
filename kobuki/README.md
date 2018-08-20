# ROS Kabuki Tutorial

## Reference
* http://wiki.ros.org/kobuki/Tutorials

## Environment
* ROS Kinetic

## Installation
* Install Kabuki
```
$ sudo apt-get install ros-kinetic-kobuki ros-kinetic-kobuki-core
```

* Dialout Group
```
$ sudo usermod -a -G dialout $USER
```
and then log out, log back in again.

* Set Udev Rule
```
$ rosrun kobuki_ftdi create_udev_rules

This script copies a udev rule to /etc to facilitate bringing
up the kobuki usb connection as /dev/kobuki.

[sudo] password for baron: 

Restarting udev

$ ls /dev/kobuki 
/dev/kobuki
```

* Keyboard Teleoperation
```
# In a first shell
$ . /opt/ros/kinetic/setup.bash
$ roslaunch kobuki_node minimal.launch --screen
# In a second shell
$ . /opt/ros/kinetic/setup.bash
$ roslaunch kobuki_keyop keyop.launch --screen
```
