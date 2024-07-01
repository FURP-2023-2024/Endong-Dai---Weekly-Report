## Weekly Report 3 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---
### Test Turtlebot3 with Cartographer Method(improved)

**Guidance link:** https://blog.csdn.net/gezongbo/article/details/123388655
**Note:** Cartographer and Turtlebot3 have been installed in Week 2 and 3.
**Here, try to connect these two independnent files!**

1. **Set environment variable TURTLEBOT3_MODEL to burger**
```bash
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc 
source ~/.bashrc
 ```

---


2. **Modify the launch file to set up the simulation environment.**
Modify the `catkin_ws/src/turtlebot3/turtlebot3_slam/launch/turtlebot3_cartographer.launch` file to 
change `$(arg configuration_basename)` to `turtlebot3_lds_2d_gazebo.lua`.

Also, add ""--extend" to every source command in .bashrc file.
e.g.
```bash
source ~/cartographer_ws/install_isolated/setup.bash --extend
export TURTLEBOT3_MODEL=burger
source ~/catkin_turtlebot3/devel/setup.bash --extend
 ```

---

3. **Open the Gazebo simulation environment.**
```bash
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

---

4. **Use the Cartographer algorithm for mapping.**
```bash
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=cartographer
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

**Effect:** Use key to control the moving of the robot.

**Below is an implements picture for RViz:**
<img width="1137" alt="Screenshot 2024-07-01 at 13 53 04" src="https://github.com/FURP-2023-2024/Endong-Dai---Weekly-Report/assets/172376395/fd98453d-fff1-451c-b060-424c90538557">

---

5. **Save map**
```bash
rosrun map_server map_saver -f ~/map
```

**Below is the saved map figure:**
![map](https://github.com/FURP-2023-2024/Endong-Dai---Weekly-Report/assets/172376395/9ed90a1b-0fc4-41e1-9b12-9345a679858d)


---
