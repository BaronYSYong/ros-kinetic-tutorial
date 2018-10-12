# README 

## Reference
* http://wiki.ros.org/tf/Tutorials

## memo
```
# rosparam set /use_sim_time true
# rosrun tf tf_remap _mappings:='[{old: /map, new: /odom}]'
# rosrun tf static_transform_publisher 0 0 0 0 0 0 1 /map /odom 100
# rosbag play --clock {rosbag.bag} /tf:=tf_old
```
