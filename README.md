Here’s the complete README in markdown code format for direct copy-pasting:

```markdown
# Wheeled Humanoid Robot Package

This package provides all necessary files to launch and visualize the wheeled humanoid robot in **Gazebo** and **RViz**. It includes CAD models, URDF files, configuration, and launch files.

## Features
- **Gazebo Simulation**: Launch the robot model in Gazebo.
- **RViz Visualization**: Visualize the robot model and LIDAR data in RViz.
- **LiDar Scanning**: Enable LIDAR data visualization for robotic sensing.
- **Robot Model**: Visualize the robot's URDF description in RViz.

## Launch Instructions

### 1. Launch Robot Model in Gazebo
To launch the robot model and URDF in Gazebo:

ros2 launch wheeled_humanoid_robot gazebo.launch.py
```
To stabilize the robot, turn off the physics and gravity option from the World tab in Gazebo and reset the Gazebo world by setting robot model pose to x,y,z,roll,pitch,yaw = (0,0,0,0,0,0).

This command will:
- Spawn the wheeled humanoid robot in Gazebo.

---

### 2. Launch Robot Model and LIDAR in RViz
To launch both Gazebo and RViz together, run:

ros2 launch wheeled_humanoid_robot debug.launch.py
```

This will:
- Start Gazebo with the robot model.
- Launch RViz for robot visualization.
- Preload necessary RViz configurations.

#### Steps to Visualize the Robot Model in RViz:
1. In RViz, open the **Display Panel**.
2. Click `Add` and select the **RobotModel** plugin.
3. Subscribe to the `/robot_description` topic:
   - This loads the robot's URDF model for visualization.

#### Steps to View Transform Frames (TF) in RViz:
1. Add the **TF** plugin in the Display Panel.
2. Ensure the robot's transform tree is visible and updates dynamically.

#### Steps to View Joint States in RViz:
1. Add the **RobotState** plugin.
2. Subscribe to the `/joint_states` topic to monitor real-time joint data.

---

### 3. Enable LIDAR Visualization
To activate LIDAR data, open a new terminal and run:
```bash
ros2 run wheeled_humanoid_robot laser_scan_relay.py
```

This command will:
- Start a node to publish LIDAR scan data to the `/scan_relay` topic.

#### Steps to Add LIDAR Data in RViz:
1. In RViz, open the **Display Panel**.
2. Click `Add` and select the **LaserScan** plugin.
3. Subscribe to the `/scan_relay` topic to visualize the LIDAR data.
4. Adjust settings like **Size** and **Color** for better visibility.
