# Use_Turtlebot3_with_SLAM".
* ### Install Dependent ROS 1 Packages

```
$ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy \
  ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc \
  ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan \
  ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python \
  ros-kinetic-rosserial-server ros-kinetic-rosserial-client \
  ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server \
  ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro \
  ros-kinetic-compressed-image-transport ros-kinetic-rqt* \
  ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers
  ```
  
  * ### Install TurtleBot3 Packages
  
  ```
$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3
```

* ### Set TurtleBot3 Model Name

  In case of TurtleBot3 Waffle Pi 
  
  ```$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc```
  
  ---------------------------------------
  
  # Gazebo Simulation
  * ### Install Simulation Package
  
```
$ cd ~/catkin_ws/src/
$ git clone -b kinetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make
```

* ### Launch Simulation World



-TurtleBot3 World

![Screenshot from 2021-07-05 01-21-31](https://user-images.githubusercontent.com/85907057/124401031-82a53a80-dd2f-11eb-962c-3c4a02b141d7.png)

```
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

* ### Run SLAM Node

![Screenshot from 2021-07-06 23-02-53](https://user-images.githubusercontent.com/85907057/124661354-130a8900-deb0-11eb-9d65-3c34ab1219a5.png)

terminal_1:

```
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

* ### To control the robot

![Screenshot from 2021-07-06 23-03-33](https://user-images.githubusercontent.com/85907057/124660551-03d70b80-deaf-11eb-88bc-b680d0b6b2c4.png)

terminal_2:

```
$ export TURTLEBOT3_MODEL=waffle_pi
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
* ### save the map , in terminal_3

![Screenshot from 2021-07-06 23-25-56](https://user-images.githubusercontent.com/85907057/124662501-98db0400-deb1-11eb-86a8-919a307887e8.png)
```
$ rosrun map_server map_saver -f ~/map
```
