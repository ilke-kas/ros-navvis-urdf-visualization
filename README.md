# ECSE473 Modern Robotic Programming Laboratory 2

This project was developed as part of ECSE 473: Modern Robotic Programming – Laboratory 2, which focused on visualizing a mobile robot model using URDF in RViz. The lab involved constructing a robot description package (navvis_description) that defines the robot’s physical structure using XACRO files, establishes static transforms between key components (e.g., base_link, imu, camera), and integrates the model with robot_state_publisher for real-time visualization in ROS Noetic.

```
  navvis_description
  ├── CMakeLists.txt
  ├── package.xml
  ├── launch
  │   ├── display.launch 
  ├── config
  │   └── config.rviz
  ├── urdf
  │   ├── robot.urdf
  │   └── robot.xacro
  └── README.md
```
### Prerequisites

In order to launch the project, you should already have:
- Installed ROS Noetic
- The joint state publisher GUI
  ```
  
    sudo apt install ros-noetic-joint-state-publisher-gui
  
  ```
- Gazebo plugins
  ```
  
    sudo apt install ros-noetic-plugins
  
  ```
- Velodyne description
  ```
  
    sudo apt install ros-noetic-velodyne-description
  
  ```
### Available Parameters to use with display.launch

The launch file takes three arguments:
-  use_robot_state_publisher:= (true|false) -  whether the robot_state_publisher will be used to launch (Added for Lab#3)
-  use_xacro:=(true|false) - whether the xacro file will be used to launch 
-  file - file name
-  use_joint_state_publisher_gui=(true|false)  whether the joint_state_publisher_gui will be used 

### View the Robot Description in rviz

- #### rviz with the joint_state_publisher GUI

  - ##### Launch by using the urdf file

  ```

    roslaunch navvis_description display.launch

  ```
  or by using some arguments:
  
   ```

    roslaunch navvis_description display.launch use_xacro:=false use_robot_state_publisher:=true use_joint_state_publisher_gui:=true

  ```
  - ##### Launch by using the xacro file

  ```

    roslaunch navvis_description display.launch use_xacro:=true

  ```
   or by using some arguments:
   ```

    roslaunch navvis_description display.launch use_xacro:=true use_robot_state_publisher:=true use_joint_state_publisher_gui:=true

  ```
- #### rviz with the joint_state_publisher GUI

  - ##### Launch by using the urdf file

  ```

    roslaunch navvis_description display.launch use_joint_state_publisher_gui:=false

  ```
     or by using some arguments:
  
   ```

    roslaunch navvis_description display.launch use_xacro:=false use_robot_state_publisher:=true use_joint_state_publisher_gui:=false

  ```

  - ##### Launch by using the xacro file

  ```

    roslaunch navvis_description display.launch use_xacro:=true use_joint_state_publisher_gui:=false

  ```
     or by using some arguments:
  
   ```

    roslaunch navvis_description display.launch use_xacro:=true use_robot_state_publisher:=true use_joint_state_publisher_gui:=false

  ```
   
   - #### rviz without both robot_state_publisher and the joint_state_publisher GUI (for purely static transformations as asked in the beggining for Lab#3)
     
  ```
      roslaunch navvis_description display.launch use_xacro:=true use_robot_state_publisher:=false use_joint_state_publisher_gui:=false

  ```
   
## Authors

  - **Ilke Kas** - *PhD at ECSE* -
    [Ilke Kas Github](https://github.com/ilke-kas)

