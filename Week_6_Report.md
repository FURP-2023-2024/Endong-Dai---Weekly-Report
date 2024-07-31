## Weekly Report 6 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---

创建一个ROS工作空间并编译一个克隆的包，以下是具体的步骤：

### 1. 创建工作空间

1. 打开终端并导航到你希望创建工作空间的目录。例如，桌面目录：
   ```bash
   cd ~/Desktop
   ```

2. 创建一个新的工作空间目录，并进入该目录：
   ```bash
   mkdir -p robot_ws/src
   cd robot_ws/src
   ```

### 2. 克隆包到src目录

在`src`目录中，克隆你希望使用的ROS包。例如，从GitHub克隆一个包：
   ```bash
   git clone https://github.com/RoboMaster/RoboRTS-Base.git
   ```

### 3. 编译工作空间

1. 返回到工作空间的根目录：
   ```bash
   cd ~/Desktop/robot_ws
   ```

2. 使用`catkin_make`命令编译工作空间：
   ```bash
   catkin_make
   ```

### 4. 设置环境

每次打开新的终端时，需要配置ROS环境变量，使新编译的包可用。你可以在`.bashrc`文件中添加下面一行来自动设置环境变量：
   ```bash
   echo "source ~/Desktop/robot_ws/devel/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```

或在每次使用前手动运行：
   ```bash
   source ~/Desktop/robot_ws/devel/setup.bash
   ```

### 例子总结

以下是完整的命令列表，结合以上所有步骤：

```bash
# 1. 创建工作空间
cd ~/Desktop
mkdir -p robot_ws/src
cd robot_ws/src

# 2. 克隆ROS包
git clone https://github.com/RoboMaster/RoboRTS-Base.git

# 3. 编译工作空间
cd ~/Desktop/robot_ws
catkin_make

# 4. 设置环境（可选）
echo "source ~/Desktop/robot_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

通过上述步骤，你可以创建一个ROS工作空间，克隆一个包并成功编译。




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
