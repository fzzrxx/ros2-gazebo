This repository contains the complete setup and implementation of a custom mobile robot defined in URDF (via Xacro), simulated in Gazebo, and fully integrated with ROS 2. The project includes a custom GZ-ROS bridge, control plugins, a camera module, and multiple launch files to modularize simulation and bring-up.

Features
--------

- Custom robot modeled using URDF/Xacro
- Simulation environment in Gazebo
- Custom bridge node for GZ <--> ROS communication
- Custom Gazebo control plugins
- Onboard camera sensor integrated with Gazebo and ROS
- Modular and reusable launch files
- Clean and extensible project structure

Tech Stack
----------

- ROS 2 (tested with Jazzy)
- Gazebo (Fortress/Ignition)
- URDF / Xacro
- C++
- Python (for launch)
- XML (for launch and bridge)

How to Launch
-------------

1. Build the Workspace

    cd ros2_ws5
    colcon build --symlink-install
    source install/setup.bash

2. Launch the Simulation

    ros2 launch my_robot_bringup my_robot_gazebo.launch.xml

Camera Module
-------------

- Configured via Gazebo's sdf tags and integrated in URDF via Xacro
- Publishes to ROS 2 topics using the custom bridge
- Supports visualization in Rviz2 and image tools

Custom GZ-ROS Bridge
--------------------

- Written from scratch to sync essential topics between Gazebo and ROS
- Handles camera, joint states, control commands, etc.
- Can be extended for other sensors and topics

Control Plugins
---------------

- Custom Gazebo plugin for differential drive / other locomotion
- Written in C++ and loaded via .sdf
- Integrated with ROS 2 topic/subscription interfaces

Testing & Visualization
-----------------------

- Use Rviz2 to visualize the robot and camera feed
- Echo ROS 2 topics to verify bridges
- Tune plugin parameters for smoother motion

TODO (Optional)
---------------

- Add lidar module
- Integrate SLAM or navigation stack
- Implement full ROS 2 ros2_control interface


Contributions
-------------

Contributions, issues, and forks are welcome. This repo is meant as both a personal learning log and a foundation for more advanced robotic simulations.

