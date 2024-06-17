
### Weekly Report 1 for FURP23/24 - Omni-directional-Robot-Collision-Awareness

---

#### Setting Up the Environment
- **Operating System**: Ubuntu 20.04 LTS
- **Framework Platform**: ROS1 Noetic
- **Simulation Platform**: Gazebo

---

#### Following ROS 21 Talk Video Tutorials 1 - 9

1. **Testing ROS Installation**
    - **Start ROS master**: 
      ```bash
      $ roscore
      ```
    - **Launch TurtleSim simulator**:
      ```bash
      $ rosrun turtlesim turtlesim_node
      ```
    - **Launch TurtleSim control node**:
      ```bash
      $ rosrun turtlesim turtle_teleop_key
      ```
    - **Verification**: Successfully control the turtle using arrow keys, confirming ROS installation.

2. **Understanding Core ROS Concepts**
    - **Node**: A process that performs computation.
    - **Topic**: A communication channel used by nodes to exchange messages.
    - **Message**: A data structure used in ROS for communication between nodes.
    - **Service**: A synchronous communication mechanism in ROS.

3. **Using ROS Command Line Tools**
    - **Example with TurtleSim**:
      - Run the three commands mentioned in section 1.
      - **View computation graph**: 
        ```bash
        $ rqt_graph
        ```
      - **List active nodes**:
        ```bash
        $ rosnode list
        ```

4. **Publishing Topic Messages**
    - **Publish a topic message**:
      ```bash
      $ rostopic pub -r 10 /turtle1/cmd_vel geometry_msgs/Twist "{linear: {x: 1.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}"
      ```
    - **Verification**: The turtle keeps moving to the right. Use `Ctrl + C` to stop the script.

5. **Publishing Service Requests**
    - **Publish a service request**:
      ```bash
      $ rosservice call /spawn "x: 5.0
      y: 5.0
      theta: 0.0
      name: 'turtle2'"
      ```
    - **Verification**: A new turtle spawns at the specified coordinates.

6. **Recording Topics**
    - **Record topics**:
      ```bash
      $ rosbag record -a -O cmd_record
      ```
    - **Verification**: Control the turtle's movements freely. Use `Ctrl + C` to stop and save.

7. **Replaying Topics**
    - **Replay topics**:
      ```bash
      $ rosbag play cmd_record.bag
      ```
    - **Verification**: Open the previously recorded file to replay the turtle's movements.

---

#### Additional Learning from ROS 21 Talk Tutorials 10 - 16

8. **Publisher Implementation**:
    - **Creating Publisher Code (C++)**:
      - Filename: `velocity_publisher.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun turtlesim turtlesim_node
      $ rosrun <your_package_name> velocity_publisher
      ```
    - **Effect**: The turtle moves in a circular pattern due to the linear and angular velocity commands.

9. **Subscriber Implementation**:
    - **Creating Subscriber Code (C++)**:
      - Filename: `pose_subscriber.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun turtlesim turtlesim_node
      $ rosrun <your_package_name> pose_subscriber
      ```
    - **Effect**: The terminal displays the position and orientation of the turtle in real-time.

10. **Topic Message Definition and Usage**:
    - **Custom Topic Message**:
      - Filename: `Person.msg`
    - **Publisher and Subscriber Code (C++)**:
      - Publisher Filename: `person_publisher.cpp`
      - Subscriber Filename: `person_subscriber.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun <your_package_name> person_publisher
      $ rosrun <your_package_name> person_subscriber
      ```
    - **Effect**: The terminal displays the published person information: name, age, and height.

11. **Client Implementation**:
    - **Creating Client Code (C++)**:
      - Filename: `turtle_spawn.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun turtlesim turtlesim_node
      $ rosrun <your_package_name> turtle_spawn_client
      ```
    - **Effect**: A new turtle named "turtle2" spawns at the specified coordinates in the turtlesim window.

12. **Server Implementation**:
    - **Creating Server Code (C++)**:
      - Filename: `turtle_command_server.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun turtlesim turtlesim_node
      $ rosrun <your_package_name> turtle_command_server
      $ rosservice call /teleport_turtle "x: 5.0 y: 5.0 theta: 0.0"
      ```
    - **Effect**: The turtle teleports to the specified coordinates (x: 5.0, y: 5.0) with the specified orientation (theta: 0.0).

13. **Service Data Definition and Usage**:
    - **Custom Service Data**:
      - Filename: `Person.srv`
    - **Server and Client Code (C++)**:
      - Server Filename: `person_server.cpp`
      - Client Filename: `person_client.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun <your_package_name> person_server
      $ rosrun <your_package_name> person_client
      ```
    - **Effect**: The terminal displays the received person information and confirms the receipt.

14. **Parameter Usage and Programming Methods**:
    - **Parameter Code (C++)**:
      - Filename: `parameter_config.cpp`
    - **ROS Terminal Commands**:
      ```bash
      $ roscore
      $ rosrun <your_package_name> parameter_config
      ```
    - **Effect**: The terminal displays the values of the parameters set in the node.

---
