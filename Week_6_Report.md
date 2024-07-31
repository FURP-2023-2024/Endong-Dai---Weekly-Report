## Weekly Report 6 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---


   ```bash
chmod +x ~/Desktop/robot_ws/src/roborts_base/src/chassis



<launch>
    <master auto="start"/>

    <!-- Load the Base Parameter -->
    <rosparam command="load" file="$(find roborts_base)/config/base.yaml" />

    <!-- Run the Base Node -->
    <node pkg="roborts_base" type="roborts_base_node" name="roborts_base_node" output="screen" respawn="true" />

    <node pkg="robort_base" type="chassis" name="chassis_node" />

    <!-- Run move_base Node -->
    <node pkg="move_base" type="move_base" name="move_base" output="screen">
        <param name="base_local_planner" value="dwa_local_planner/DWAPlannerROS"/>
    </node>
</launch>
   ```




### 1. Unitree Go1 simulation install and apply

**Guidance link:** http://t.csdnimg.cn/uHlkK
http://t.csdnimg.cn/XUOiM

**Note:** 
Unitree_ros: Mainly used for simulation (rviz, gazebo), it includes some upper-level motion algorithms. It depends on unitree_ros_to_real.

Unitree_ros_to_real: Encapsulates various data types and motor position, torque, and speed modes. It depends on unitree_legged_sdk.

Unitree_legged_sdk: Encapsulates the communication protocol and simple robot motion modes. This is necessary if you want to connect to a real robot dog.

1. **Clone omni3_robot package**
```bash
cd catkin_ws/src
git clone https://github.com/unitreerobotics/unitree_ros_to_real
git clone https://github.com/unitreerobotics/unitree_ros
git clone https://github.com/unitreerobotics/unitree_guide
 ```

---


2. **View the model in RVIZ**
```bash
roslaunch laikago_description laikago_rviz.launch
 ```
<img width="1338" alt="Screenshot 2024-07-19 at 12 43 28" src="https://github.com/user-attachments/assets/ed10ec56-660d-4ea8-934c-dd7840c27578">

---

3. **View the model in RVIZ and send command**
```bash
roslaunch unitree_gazebo normal.launch rname:=a1 wname:=stairs
rosrun unitree_controller unitree_servo
```

Robot will stand up

<img width="662" alt="Screenshot 2024-07-19 at 12 46 04" src="https://github.com/user-attachments/assets/ab7e3dde-6c2d-4b1d-b6cb-f490af21042e">
<img width="583" alt="Screenshot 2024-07-19 at 12 46 29" src="https://github.com/user-attachments/assets/de6a21a4-d04b-42fb-a8ff-39d61090f455">


---
