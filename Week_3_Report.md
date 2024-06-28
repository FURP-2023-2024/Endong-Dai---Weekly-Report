### Weekly Report 3 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---

#### Install and Test Turtlebot3 

**Based on the article:**https://blog.csdn.net/weixin_51015707/article/details/121522342

1. **Install Turtlebot3 dependencies**
    
   ```bash
      sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc ros-noetic-rgbd-launch ros-noetic-depthimage-to-laserscan ros-noetic-rosserial-arduino ros-noetic-rosserial-python ros-noetic-rosserial-server ros-noetic-rosserial-client ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro  ros-noetic-compressed-image-transport ros-noetic-rqt-image-view ros-noetic-gmapping ros-noetic-navigation  ros-noetic-interactive-markers rviz
      ```

---


2. **Create a project and install Turtlebot3**

```bash
mkdir catkin_turtlebot3
cd catkin_turtlebot3
mkdir src
cd src
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
cd ..
catkin_make
```

---

3. **Turtlebot3 downloaded and compiled**
```bash
echo "export TURTLEBOT3_MODEL=waffle" >> ~/.bashrc
echo "source ~/catkin_turtlebot3/devel/setup.bash" >> ~/.bashrc
echo $ROS_PACKAGE_PATH

```

---

4. **Use Turtlebot3 for mapping.**
```bash
cd catkin_turtlebot3
roscore
roslaunch turtlebot3_gazebo turtlebot3_world.launch
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
**Effect:** Use key to control the moving of the robot.

**Below are some implements pictures:**

<img width="1109" alt="Screenshot 2024-06-28 at 13 15 36" src="https://github.com/FURP-2023-2024/Endong-Dai---Weekly-Report/assets/172376395/f571fd5b-1173-4024-b2e0-ab24729e80f2">
<img width="849" alt="Screenshot 2024-06-28 at 13 15 59" src="https://github.com/FURP-2023-2024/Endong-Dai---Weekly-Report/assets/172376395/6acb2d4d-09d8-4d16-b962-99c4ada07498">

**Note:** Use gmapping here. Need to change to cartograher method!

---
