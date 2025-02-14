# TurtleBot3 Burger Robot Project

This project involves setting up and controlling a TurtleBot3 Burger robot in a Gazebo simulation environment, performing SLAM (Simultaneous Localization and Mapping), and saving the generated map for navigation.

## Prerequisites

- ROS (Robot Operating System) installed
- TurtleBot3 packages installed
- Gazebo simulator installed

## Project Overview

The TurtleBot3 Burger robot project is designed to provide hands-on experience with robotics, simulation, and autonomous navigation. By following this guide, you will learn how to:

- Set up a simulated environment for the TurtleBot3 Burger robot.
- Control the robot's movement using teleoperation.
- Perform SLAM to create a map of the environment.
- Save the generated map for future navigation tasks.
- Navigate the robot autonomously using the saved map.

## Applications

This project has several practical applications, including:

- **Robotics Education**: Gain a deeper understanding of robotics concepts, ROS, and Gazebo simulation.
- **Research and Development**: Use the TurtleBot3 platform for developing and testing new algorithms in robotics.
- **Autonomous Navigation**: Implement and test autonomous navigation strategies in a simulated environment.
- **SLAM and Mapping**: Learn and apply SLAM techniques to create accurate maps of unknown environments.

## Steps

### 1. Export the TurtleBot3 Model

First, export the TurtleBot3 model as `burger`:
```bash
export TURTLEBOT3_MODEL=burger
```

### 2. Launch the Gazebo World

Next, launch the Gazebo world with the Burger robot in it:
```bash
roslaunch turtlebot3_gazebo turtlebot3_house.launch
```
![IMG-20250124-WA0004](https://github.com/user-attachments/assets/14e4931e-0eaf-4a72-9797-7b5df4212256)

### 3. Control the Robot Movement

To control the movement of the robot, use the teleop key node:
```bash
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

```

![IMG-20250124-WA0001](https://github.com/user-attachments/assets/833283f9-5c88-43fb-9a4e-cfe3f31ce438)
### 4. Run SLAM Node:

run the slam node in the other termial 
```bash
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
Now rviz(ros visualization ) tool open for mapping.explore your evironment every space to get cleaar mapping for localization
![IMG-20250124-WA0005](https://github.com/user-attachments/assets/e9bebf7b-0013-4383-ade4-a41dd6d9569a)

### 5. Save the Map

After completely exploring the environment, save your map using the map saver node:

```bash
rosrun map_server map_saver -f ~/map
```
Ensure the `map.yaml` file is saved in your home folder.
![IMG-20250124-WA0002](https://github.com/user-attachments/assets/213190b4-a0d6-45cb-b11f-35aa14b1c397)

### 6. Run the Navigation Node

Finally, run the navigation node with the saved map:

```bash
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml
```
![IMG-20250124-WA0003](https://github.com/user-attachments/assets/3d778c45-93db-4270-b67a-74e04ece3962)

## Conclusion

By following these steps, you will be able to set up, control, and navigate your TurtleBot3 Burger robot in a simulated environment using ROS and Gazebo. This project not only enhances your understanding of robotics but also provides practical skills in autonomous navigation and SLAM. Happy robotics!



