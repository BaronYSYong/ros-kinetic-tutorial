# ROS Kinetic

## Reference
* https://github.com/ros2/ros2/wiki
* http://wiki.ros.org/topic_tools/throttle
* [nodelet](http://cryborg.hatenablog.com/entry/2016/09/19/154712)

## Sample
* publish message in command
```
$ rostopic pub my_topic std_msgs/String "hello there"
```
* create package
```
# catkin_create_pkg <package_name> [depend1] [depend2] [depend3]
# e.g.
$ catkin_create_pkg beginner_tutorials std_msgs rospy roscpp
```
```
$ rosrun tf tf_echo /map /odom
```
