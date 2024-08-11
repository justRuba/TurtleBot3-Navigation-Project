# TurtleBot3-Navigation-Project
This project involves setting up and running TurtleBot3 in a Gazebo simulation environment, creating a map using SLAM, and enabling autonomous navigation using the generated map.

## Table of Contents
- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Creating a Map (SLAM)](#creating-a-map-slam)

## Overview
This project demonstrates how to set up TurtleBot3 in a simulated environment, create a map using Simultaneous Localization and Mapping (SLAM), and use that map for autonomous navigation. The steps include installing necessary packages, launching the TurtleBot in Gazebo, mapping the environment, and navigating using the saved map.

## Prerequisites
Before you begin, ensure you have the following installed:
- Ubuntu 20.04
- ROS Noetic
- TurtleBot3 packages

## Installation

### Step 1: Install TurtleBot3 Packages
Start by installing the TurtleBot3 and TurtleBot3 simulation packages:

```bash
sudo apt-get update
sudo apt-get install ros-noetic-turtlebot3 ros-noetic-turtlebot3-simulations
```

Set the TurtleBot model (Burger, Waffle, or Waffle Pi):

```bash
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
source ~/.bashrc
```

### Step 2: Install TurtleBot3 Simulation Package

Get the TurtleBot3 Gazebo simulation package:

```bash
sudo apt-get install ros-noetic-turtlebot3-gazebo
```

## Creating a Map (SLAM)

## Step 3: Launch the TurtleBot in Gazebo

Open a terminal and launch the TurtleBot in the Gazebo simulation environment:

```bash
roslaunch turtlebot3_gazebo turtlebot3_world.launch
```

## Step 4: Launch the SLAM Node

In another terminal, launch the SLAM node to begin mapping:

```bash
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```

## Step 5: Control the TurtleBot to Create the Map

Open a new terminal and launch the teleoperation node to control the TurtleBot using the keyboard:

```bash
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```

Use the following keys to control the TurtleBot:

- W: Move forward
- S: Move backward
- A: Turn left
- D: Turn right
- X: Stop moving

Move the TurtleBot around to map the environment.

## Step 6: Save the Map

Once finished mapping, save the map by opening a new terminal and running:

```bash
rosrun map_server map_saver -f ~/map
```

![WhatsApp Image 2024-08-12 at 01 52 59_d4a8ddbc](https://github.com/user-attachments/assets/722add36-edc3-4a2e-87de-1c443b3214b8)


