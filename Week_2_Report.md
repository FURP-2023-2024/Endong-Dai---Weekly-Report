
### Weekly Report 2 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---

#### Following ROS 21 Talk Video Tutorials 17 - 21

1. **TF Coordinate Transformation**
    - **TF Package**: Transforming the relationship between local and global coordinate systems 5 seconds ago.
    - **Implementation Code**:
      ```bash
      sudo apt-get install ros-melodic-turtle-tf
      roslaunch turtle_tf turtle_tf_demo.launch
      rosrun turtlesim turtle_teleop_key
      rosrun tf view_frames
      ```
    - **Effect**: Controlling Turtle 1's movement, Turtle 2 automatically follows (taking shortcuts).

    - **Listening for 5 seconds and saving all coordinate relationships**:
      <img width="901" alt="Screenshot 2024-06-19 at 17 41 50" src="https://github.com/FURP-2023-2024/Endong-Dai---Weekly-Report/assets/172376395/7a8141bb-ac3e-4792-88ba-1de0eb243ca2">

    - **Opening the visualization tool**:
      ```bash
      rosrun rviz rviz -d `rospack find turtle_tf`/rviz/turtle_rviz.rviz
      ```
    - **Effect**: Visualizing the real-time relationship between the two turtles (local coordinates) and the world (global coordinates).
    
    - **View Frames Result**:
      <img width="964" alt="Screenshot 2024-06-19 at 18 10 02" src="https://github.com/FURP-2023-2024/Endong-Dai---Weekly-Report/assets/172376395/924c3eb5-702c-45b4-b1f3-3af6d52177f2">


---


2. **Broadcasting and Listening to TF Coordinates (Code)**
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

### 3. Using Launch Files in ROS

Launch files are used to start multiple nodes with a single command. They allow for easier management of parameters and node execution.

#### Launch File Syntax
- `<launch>`: Root element of the launch file.
- `<node>`: Defines a ROS node that will be launched.
- `<param>`: Sets parameters on the parameter server.
- `<rosparam>`: Used for loading parameters from YAML files.
- `<arg>`: Defines an argument that can be passed to the launch file.

#### Examples of Launch Files
- `simple.launch`: A basic launch file to start nodes.
- `turtlesim_parameter_config.launch`: Configures parameters for the Turtlesim node.
- `start_tf_demo_c++.launch`: Starts a TF demonstration using C++ nodes.
- `turtlesim_remap.launch`: Remaps topics for the Turtlesim node.

Using these launch files can simplify the process of starting and managing multiple ROS nodes, especially for complex systems.


---
