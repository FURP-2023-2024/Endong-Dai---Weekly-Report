## Weekly Report 6 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---


   ```bash
Section "Monitor"
  Identifier "Monitor0"
  HorizSync 28.0-80.0
  VertRefresh 48.0-75.0
  # https://arachnoid.com/modelines/
  # 1024x768 @ 60.00 Hz (GTF) hsync: 47.70 kHz; pclk: 64.11 MHz
  Modeline "1360x768_60.00" 64.11 1024 1080 1184 1344 768 769 772 795 -HSync +Vsync
EndSection
Section "Device"
  Identifier "Card0"
  Driver "dummy"
  VideoRam 256000
EndSection
Section "Screen"
  DefaultDepth 24
  Identifier "Screen0"
  Device "Card0"
  Monitor "Monitor0"
  SubSection "Display"
    Depth 24
    Modes "1360x768_60.00"
  EndSubSection
EndSection
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
