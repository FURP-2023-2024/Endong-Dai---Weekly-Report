### Weekly Report 3 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---

#### Install and Test Turtlebot3 

**Based on the article:**https://blog.csdn.net/weixin_51015707/article/details/121522342

1. **Install Turtlebot3 dependencies**
    - **TF Package**: Transforming the relationship between local and global coordinate systems 5 seconds ago.
    - **Implementation Code**:
      ```bash
      sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc ros-noetic-rgbd-launch ros-noetic-depthimage-to-laserscan ros-noetic-rosserial-arduino ros-noetic-rosserial-python ros-noetic-rosserial-server ros-noetic-rosserial-client ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro  ros-noetic-compressed-image-transport ros-noetic-rqt-image-view ros-noetic-gmapping ros-noetic-navigation  ros-noetic-interactive-markers rviz
      ```

---


2. **Create a project and install Turtlebot3**
Create the package:
```sh
$ cd ~/catkin_ws/src
$ catkin_create_pkg learning_tf roscpp rospy tf turtlesim
```

Import the C++ files `turtle_tf_broadcaster` and `turtle_tf_listener`.

Run the ROS program and the related C++ files:
```sh
$ roscore
$ rosrun turtlesim turtlesim_node
$ rosrun learning_tf turtle_tf_broadcaster __name:=turtle1_tf_broadcaster /turtle1
$ rosrun learning_tf turtle_tf_broadcaster __name:=turtle2_tf_broadcaster /turtle2
$ rosrun learning_tf turtle_tf_listener
$ rosrun turtlesim turtle_teleop_key
```

Effect: Similar to the first example, by broadcasting and listening to the TF coordinate systems, Turtle 2 will follow Turtle 1's movement.


---
