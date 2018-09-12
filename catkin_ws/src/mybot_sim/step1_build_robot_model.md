# Step 1: Simulating Robot Models for ROS

## Overview

* mybot_ws
    * src
        * mybot_control
            * config
                * mybot_control.yaml
            * launch
                * mybot_control.launch
            * CMakeLists.txt
            * package.xml
        * mybot_description
            * launch
                * mybot_rviz.launch
            * urdf
                * macros.xacro
                * materials.xacro
                * mybot.gazebo
                * mybot.xacro
            * CMakeLists.txt
            * package.xml
        * mybot_gazebo
            * launch
                * mybot_world.launch
            * worlds
                * mybot.world
            * CMakeLists.txt
            * package.xml

* mybot_description specifies the entire robot structure as links and joints and can launch the model in rviz.
* mybot_gazebo launches the model in the gazebo environment and contains different simulation worlds.

* mybot_control (not used) enable control over joints of our model so that it can move around.

```
$ cd ~
$ mkdir mybot_ws
$ cd mybot_ws
$ catkin init
$ mkdir src
$ catkin build
$ echo "source ~/mybot_ws/devel/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```
In the src folder are three main packages, {MODEL}_control, {MODEL}_description, {MODEL}_gazebo. We set {MODEL} = mybot. To create a package: catkin_create_pkg {PKG_NAME} {PKG_DEPENDENCIES}. In this case, we have no {PKG_DEPENDENCIES} = "".
```
$ cd ~/mybot_ws/src/
$ catkin_create_pkg mybot_control
$ catkin_create_pkg mybot_description
$ catkin_create_pkg mybot_gazebo
```

## Create the Robot Model (URDF)
In ~/mybot_ws/src/mybot_description/urdf, there are four files:

* mybot.xacro: primary file that loads the other three files and contains only URDF items like joints and links
* mybot.gazebo: contains gazebo-specific labels that are wrapped within gaz
* materials.xacro: maps strings to colors
* macros.xacro: macros to help simplify

