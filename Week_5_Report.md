## Weekly Report 5 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---


### 1. Try Omni-Robot Package with Keyboard

**Guidance link:** https://github.com/YugAjmera/omni3ros_pkg
https://github.com/YugAjmera/teleop_keyboard_omni3 (for keyboard)

**Note:** Failure to view in Gazebo because it still need to install the model for this three-wheeled omnidirectional robots

1. **Clone omni3_robot package**
```bash
cd catkin_ws/src
git clone "https://github.com/YugAjmera/omni3ros_pkg"
cd .. 
catkin_make
source ./devel/setup.bash
source ~/.bashrc
 ```

---


2. **View the model in Gazebo and RVIZ**
```bash
roslaunch omni3ros_pkg urdf_gazebo_view.launch
roslaunch omni3ros_pkg urdf_rviz_view.launch
 ```

---

3. **Keyboard Control**
```bash
cd ~/catkin_ws/src
git clone https://github.com/YugAjmera/teleop_keyboard_omni3
cd ~/catkin_ws
catkin_make
source ~/catkin_ws/devel/setup.bash
source ~/.bashrc
rosrun teleop_keyboard_omni3 teleop_keyboard_omni3.py 
```

---


**Note:** Finally, keyboard works, but omin3_robot fails due to lack of the omni3_robot model.


---

### 2. Install and Build RoboRTS-Base
```bash
sudo apt-get update && sudo apt-get install -y --no-install-recommends \
     ros-${ROS_DISTRO}-tf ros-${ROS_DISTRO}-nav-msgs ros-${ROS_DISTRO}-geometry-msgs libgoogle-glog-dev
git clone https://github.com/RoboMaster/RoboRTS-Base.git catkin_ws/src
cd catkin_ws
catkin_make
```

---
