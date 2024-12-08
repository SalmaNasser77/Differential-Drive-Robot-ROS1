# 🚗 Differential-Drive Robot with ROS1 Noetic, Gazebo, and RViz

This repository contains a **ROS1 Noetic** package for simulating and visualizing a differential-drive mobile robot in **Gazebo** and **RViz**. The robot's configuration and design are defined using **URDF (Unified Robot Description Format)**.

## 🎥 Demonstration Video
https://github.com/user-attachments/assets/4e858dc2-84f2-4b73-b2d8-a825b7e698cf


## 📂 Repository Structure

- **`launch/`**  
  Contains launch file for initializing the simulation environment:  
  - **`display.launch`**:  
    This file launches:
    - 🚀 The robot URDF in the parameter server.  
    - 🤖 `robot_state_publisher` for broadcasting robot transforms.  
    - ⚙️ `joint_state_publisher` for manual control of joints in RViz.  
    - 🌍 Gazebo simulation with the specified world (`rc_world.world`).  
    - 🛠️ The robot in Gazebo via `spawn_model`.  
    - 👀 RViz visualization with a predefined configuration.

- **`meshes/`**  
  Contains the mesh file:
  - **`hokuyo.dae`**: Represents the Hokuyo lidar sensor used in the robot model.

- **`urdf/`**  
  Includes files defining the robot's design:
  - **`diff_drive.urdf`**: URDF file describing the differential-drive robot's structure.  
  - **`differential_robot.gv`** & **`differential_robot.pdf`**: Graphical representations of the robot's kinematic structure.

- **`worlds/`**  
  Contains the world file:
  - **`rc_world.world`**: Defines the environment where the robot spawns in Gazebo.

- **`CMakeLists.txt`** & **`package.xml`**  
  Standard files for defining the ROS package dependencies and build process. 🛠️

## ✨ Features

1. **🌌 Simulation in Gazebo**:  
   The robot is spawned in a custom world and can interact with the simulation environment.
   
2. **🔍 Visualization in RViz**:  
   Displays the robot model and sensor data for debugging and monitoring.

3. **🛠️ URDF Robot Model**:  
   A detailed URDF representation of a differential-drive mobile robot with a Hokuyo lidar sensor, Camera sensor, and IMU sensor.

## 📋 Prerequisites

- **ROS1 Noetic** installed on your system.  
- **Gazebo** and **RViz** are required for simulation and visualization.  

## 🚀 How to Use

1. Clone the repository inside <ROS1_WS/SRC>:  
   ```bash
   git clone https://github.com/SalmaNasser77/Differential-Drive-Robot-ROS1.git
   cd <ROS1_WS>
2. Build the package:
   ```bash
    catkin_make
    source devel/setup.bash
3. Launch the simulation and visualization:
   ```bash
    roslaunch diff_drive display.launch

This will:
- 📜 Load the robot model into the parameter server.
- 🌍 Start Gazebo with the specified world.
- 🤖 Spawn the robot in the simulation environment.
- 🔍 Launch RViz for visualization.

## 🌟 Future Enhancements
- 🚀 Adding navigation capabilities using the ROS navigation stack.
- 🔦 Optimizing URDF using included xacro.
- 🌍 Improving the world environment for testing robot behaviors.


## ⌨️ Moving using teleop node
- for this, you'll need to install teleop_twist_keyboard package to use teleop_twist_keyboard.py node as follows:
   ```bash
    rosrun teleop_twist_keyboard teleop_twist_keyboard.py
