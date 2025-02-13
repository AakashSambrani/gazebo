
# TurtleBot3 Navigation in Gazebo

**MIT License**

## Description

This project demonstrates the simulation of a TurtleBot3 Waffle Pi navigating through a custom 3D world and its corresponding static map in Gazebo. The robot uses ROS2 to interact with the environment, localize itself, and perform navigation tasks.

## Features

- **3D World Creation**: A custom 3D environment is designed in Gazebo.
- **TurtleBot3 Simulation**: The TurtleBot3 Waffle Pi model is spawned and controlled in the simulation.
- **Navigation**: The robot performs navigation tasks using ROS2 packages for mapping, localization, and path planning.
- **Recording**: The simulation is recorded to capture the navigation process.
- **Static Map**: A static map of the environment is created and used for navigation.

## Table of Contents

- [Installation](#installation)
- [Setup and Configuration](#setup-and-configuration)
- [Usage](#usage)
- [Examples](#examples)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Installation

Follow the steps below to set up the project:

### 1. Clone the repository:

```bash
git clone https://github.com/yourusername/turtlebot3-navigation.git
cd turtlebot3-navigation
```

### 2. Install Dependencies:

Make sure you have ROS2 Humble installed. Then, install the necessary dependencies:

```bash
sudo apt update
sudo apt install -y ros-humble-turtlebot3-gazebo ros-humble-navigation2 ros-humble-map-server
```

### 3. Set Up the ROS2 Workspace:

```bash
source /opt/ros/humble/setup.bash
colcon build
source install/setup.bash
```

## Setup and Configuration

### 1. Configure the TurtleBot3 Model:

Make sure you have the correct TurtleBot3 model settings by setting the model environment variable:

```bash
export TURTLEBOT3_MODEL=waffle_pi
```

### 2. Create the 3D World in Gazebo:

The world and its static map are defined using `.world` and `.yaml` files. Modify these files as needed to customize the environment.

- `my_world.world`: This is the 3D world file in Gazebo.
- `map.yaml`: This file contains the configuration for the static map, which is used for navigation.

### 3. Add the Static Map to the Environment:

Use the `map_server` to load the map for navigation in ROS2:

```bash
ros2 run map_server map_server map.yaml
```

## Usage

### 1. Launch the Gazebo Simulation:

Launch the simulation environment with the TurtleBot3 model and the static map:

```bash
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

This command will start Gazebo with the TurtleBot3 model and the static map you created.

### 2. Launch Navigation:

Once the simulation is running, start the navigation process by running:

```bash
ros2 launch turtlebot3_navigation2 navigation2_launch.py
```

This will initiate the robot's navigation tasks, including localization and path planning.

### 3. Record the Navigation Process:

To record the robot's movements during the simulation, use the `ros2 bag` command:

```bash
ros2 bag record -a
```

This will record all topics during the navigation process.

## Examples

Here’s an example of how the TurtleBot3 navigates the environment:

- The robot starts at a specified location in the Gazebo world.
- Using ROS2, the robot localizes itself on the static map.
- The robot plans a path and navigates to the target location autonomously.
- The entire navigation process is captured and saved in a video format.

## Contributing

We welcome contributions to this project! To contribute:

1. Fork the repository.
2. Create a new branch for your feature (e.g., `git checkout -b feature-name`).
3. Make your changes and commit them (e.g., `git commit -m 'Add new feature'`).
4. Push your branch to your fork (e.g., `git push origin feature-name`).
5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **ROS2**: For providing a powerful framework for robotics simulation.
- **TurtleBot3**: For their easy-to-use robot models for Gazebo and ROS2.
- **Gazebo**: For the simulation platform used in this project.
- **OpenAI**: For inspiring innovative approaches to AI in robotics and simulations.

---
