
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

2. **TF view_frames**:
    - **Listening for 5 seconds and saving all coordinate relationships**:
      ![TF_view effect](file-2039s5B3cciu2D438hVvLr6b.png)
    - **Opening the visualization tool**:
      ```bash
      rosrun rviz rviz -d `rospack find turtle_tf`/rviz/turtle_rviz.rviz
      ```
    - **Effect**: Visualizing the real-time relationship between the two turtles (local coordinates) and the world (global coordinates).
    
    - **View Frames Result**:
      ![View Frames Result](file-INhqY273JQtKQILxgnFI3FgH.png)

---
