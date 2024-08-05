## Week 8
- **Build and Test RoboRTS-Base and navigation Package**

## Weekly Report 8 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---


### 1. Build and Test RoboRTS-Base Package

1. **Build and Compile**
```bash
mkdir -p ~/car_ws/src
cd ~/car_ws/src
git clone https://github.com/RoboMaster/RoboRTS-Base.git
cd ~/car_ws
catkin_make
echo "source ~/car_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc
 ```

---


2. **Configuration**
```bash
./src/scripts/udev.sh create
./src/scripts/udev.sh check
./src/scripts/udev.sh status
 ```
---

3. **Run**
```bash
source devel/setup.bash
roslaunch roborts_base base.launch
 ```

**Note:** 
Modify
```bash
serial_port : "/dev/serial_sdk"
load_module : [ "chassis", "gimbal", "referee_system" ]
 ```

To
```bash
serial_port : "/dev/ttyACM0"
load_module : [ "chassis"]
 ```

**Now, after running "roslaunch.base", remote control can control the car.“”**

**Control lidar:**
```bash
roslaunch rplidar _ros rplidar_a2m8.launch
 ```

**Then, open RVIZ to display the result:**
```bash
rosrun rviz rviz
 ```
---


### 2. Build and Test Navigation Package

1. **Build and Compile**
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
**Note:** turtlebot3-navigation and turtlebot3-slam are important for cartographer.

**problem:** Don't know how to link RoboRTS-Base with navigation package.  
Don't know how to send the lidar data to another package: Navigation.


---
