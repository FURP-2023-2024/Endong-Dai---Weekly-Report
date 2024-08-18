## Week 9
- **Deployed the Cartographer algorithm and Navigation package**

## Weekly Report 9 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---

## Overview
In the final week, we successfully deployed the Cartographer algorithm on the vehicle to enable mapping functionality. We were also able to load pre-built maps to achieve 2D Nav goal navigation.

## Navigation Packages

### `roborts_base`
This package is used to start the vehicle's chassis, including odometry and other information.
- **Startup Command:**
  ```bash
  catkin_ws/src/RoboRTS-Base/Roberts_base/launch roslaunch base.launch
  ```

### `rplidar_ros`
This package is used to start the vehicle's LiDAR and publish the LiDAR node.
- **Startup Command:**
  ```bash
  rplidar/src/rplidar_ros/launch roslaunch rplidar_a2m8.launch
  ```

### `my_navigation_pkg`
This is the navigation package.
- **Startup Command:**
  ```bash
  catkin_ws_car/src/my_navigation_pkg roslaunch move_base.launch
  ```

### `cartographer`
This package subscribes to the LiDAR node to perform mapping and is a type of SLAM algorithm.
- **Startup Command:**
  ```bash
  cartographer/src/cartographer_ros/cartographer_ros/launch roslaunch cartographer
  ```

## Remote Connection
Use MobaXterm to SSH connect to the vehicle.

## IAMET_L2 map：
![image](https://github.com/user-attachments/assets/0f327a0a-3cc2-4b39-a876-92a76de271d4)


## Results and Discussion
The mapping obtained from the Cartographer algorithm clearly shows the layout of the second floor of the IAMET Building. The map reveals many black spots inside the classrooms, clear scanning results at glass windows, and some curved walls.     

This is primarily due to numerous chairs inside the classrooms, which affected the LiDAR's scanning of the terrain. While the LiDAR handles distant obstacles well, it cannot recognize glass obstacles. Combining cameras with LiDAR could help address this issue. The curved walls are due to long benches blocking some areas, which the vehicle couldn't access for scanning.

