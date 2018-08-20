FROM ubuntu:xenial

RUN export UBUNTU_VERSION=xenial && export ROS_VERSION=kinetic && \
	apt-get update && apt-get install -y \
	software-properties-common wget && \
	add-apt-repository "deb http://packages.ros.org/ros/ubuntu $UBUNTU_VERSION main" && \
	wget https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -O - | apt-key add - && \
	apt-get update && \
    apt-get install -y \
    ros-$ROS_VERSION-desktop-full "ros-$ROS_VERSION-tf2-*" "ros-$ROS_VERSION-camera-info-manager*" --yes \
	autotools-dev ccache doxygen dh-autoreconf git liblapack-dev \
	libblas-dev libgtest-dev libreadline-dev libssh2-1-dev pylint \
	clang-format-3.8 python-autopep8 python-catkin-tools python-pip \
	python-git python-setuptools python-termcolor python-wstool \
	libatlas3-base --yes vim && \
	pip install requests && \    
	rosdep init && rosdep update && \
    echo ". /opt/ros/$ROS_VERSION/setup.bash" >> ~/.bashrc && \
    source ~/.bashrc && \ 
	apt-get install -y ccache &&\
	echo 'export PATH="/usr/lib/ccache:$PATH"' | tee -a ~/.bashrc &&\
	source ~/.bashrc && echo $PATH && \
	ccache --max-size=10G
	
    
