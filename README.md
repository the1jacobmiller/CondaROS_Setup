# Conda-ROS Set Up Steps
Steps to set up a conda environment for ROS with python3.

## Set up conda environment
1. conda create --name ros_env --channel conda-forge ros-core ros-actionlib ros-dynamic-reconfigure python=3.X
2. conda activate ros_env
3. Install any other dependencies with conda or pip

## Compile cv_bridge with python3
1. If workspace does not already contain vision_opencv
	- cd src; git clone -b <ros_distro> https://github.com/ros-perception/vision_opencv.git
	- Change find_package(Boost REQUIRED python3) to find_package(Boost REQUIRED python3X) in vision_opencv/cv_bridge/CMakeLists.txt
2. catkin config -DPYTHON_EXECUTABLE=/home/username/anaconda3/envs/ros/bin/python3.Xm -DPYTHON_INCLUDE_DIR=/home/username/anaconda3/envs/ros/include/python3.Xm -DPYTHON_LIBRARY=/home/username/anaconda3/envs/ros/lib/libpython3.Xm.so
3. catkin config install
4. catkin_make
5. source devel/setup.sh
