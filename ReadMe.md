Written by Leon RyuWoon Jung

This package refers to the [MIT Duckie Town source](https://github.com/duckietown/Software)

You can find where the progress stopped by searching 'progress 3 stopped here' statement.

# Install
The following are needed to be installed or downloaded

* turtlebot3_auto meta package
$ ~/catkin_ws/src && git clone https://github.com/ROBOTIS-Leon/turtlebot3_auto.git

* turtlebot3
$ ~/catkin_ws/src && git clone https://github.com/ROBOTIS-GIT/turtlebot3.git

* camera_umd
$ sudo apt-get install libv4l-dev
$ ~/catkin_ws/src && git clone https://github.com/ktossell/camera_umd.git

* install the others
sudo apt-get install ros-kinetic-tf-conversions ros-kinetic-cv-bridge ros-kinetic-image-transport ros-kinetic-camera-info-manager ros-kinetic-theora-image-transport ros-kinetic-joy ros-kinetic-image-proc -y
sudo apt-get install ros-kinetic-compressed-image-transport -y
sudo apt-get install libyaml-cpp-dev -y
sudo apt-get install libblas-dev liblapack-dev libatlas-base-dev gfortran

# Run
These packages can be launched by following commands

* run camera node
$ roslaunch turtlebot3_auto_sensor image_get_usb_camera.launch

* run color balancing node (if necessary... you don't need to run this in some cases)
$ roslaunch turtlebot3_auto_sensor image_proc_color_balancing.launch

* send Bool 'True' message for activating color balancing node (if necessary... you don't need to run this in some cases)
$ rostopic pub /click std_msgs/Bool True

* run line detection node
$ roslaunch turtlebot3_auto_brain_recognitive detect_line.launch

* run line filter node
$ roslaunch lane_filter lane_filter_node.launch
