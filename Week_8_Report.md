```bash
<launch>
  <!-- 启动 move_base -->
  <node name="move_base" pkg="move_base" type="move_base" output="screen">
    <param name="base_global_planner" value="navfn/NavfnROS"/> <!-- 全局规划器 -->
    <param name="base_local_planner" value="base_local_planner/TrajectoryPlannerROS"/> <!-- 局部规划器 -->
    <rosparam command="load" file="$(find my_navigation_pkg)/config/costmap_common_parameters.yaml"/>
    <rosparam command="load" file="$(find my_navigation_pkg)/config/local_costmap.yaml"/>
    <rosparam command="load" file="$(find my_navigation_pkg)/config/global_costmap.yaml"/>
  </node>

  <!-- 启动 AMCL -->
  <node name="amcl" pkg="amcl" type="amcl" output="screen">
    <rosparam command="load" file="$(find my_navigation_pkg)/config/amcl_params.yaml"/>
    <param name="odom_frame_id" value="odom"/>
    <param name="base_frame_id" value="base_link"/>
    <param name="global_frame_id" value="map"/>
    <param name="tf_buffer_size" value="5.0"/>
  </node>

  <!-- 启动 map_server -->
  <arg name="map_file" default="/home/noetic/Desktop/my_map.yaml"/> <!-- 修改为实际地图位置 -->
  <node name="map_server" pkg="map_server" type="map_server" args="$(arg map_file)"/>

  <!-- 启动 ROS TF 变换 -->
  <!-- 将 map 到 base_link 改为 map 到 odom -->
  <node pkg="tf" type="static_transform_publisher" name="map_to_odom" args="0 0 0 0 0 0 map odom 100"/>

  <!-- 需要一个节点发布 odom 到 base_link 的变换，例如里程计节点 -->
</launch>
 ```



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
