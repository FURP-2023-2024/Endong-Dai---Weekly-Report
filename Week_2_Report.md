
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
