# ECE/MAE 148 Final Project
# Autonomous Parking
## Team 6 – Summer Session 2 2025

### Team Members
- Jordan Taylor - Electrical and Computer Engineering
- Elisha Sengupta - Electrical and Computer Engineering
- Keanu Santos-Frost - Computer Science and Engineering
- Justin Gamm - Cognitive Science

### Abstract
Our project focused on building an autonomous navigation stack for the UCSD Robocar using ROS2. The car was equipped with an LD06 LiDAR, an OAK-D camera, and a VESC motor controller. We implemented a modular navigation pipeline where sensor data is processed through dedicated nodes (cone detection, stop line detection, and LiDAR processing) and then fused in a high-level behavior node to control the car’s movements.

### What We Promised
Cone detection from OAK-D camera input
Stop line detection for intersections
LiDAR-based distance sensing and obstacle awareness
Behavior node combining inputs to control the car through the VESC

### Accomplishments
- OAK-D camera launched and published image data
- Modular design: cone_detection_node, lidar_processor_node, stop_line_detector, and behavior_node
- Unified launch file (all_components.launch.py) that reads from car_config.yaml
-  Parameter-based configuration (pkg_locations_ucsd.yaml) to enable/disable sensors and nodes

### Hardware
- UCSD Robocar platform
- LD06 LiDAR sensor
- OAK-D depth camera
- VESC motor controller with odometry
- Jetson Nano running ROS2 Foxy in Docker

### Software
- ROS2
- Dockerized development environment
- Custom ROS2 package: ucsd_robocar_nav2_pkg
- Nodes:
  - cone_detection_node.py
  - lidar_processor_node.py
  - stop_line_detector.py
  - behavior_node.py

### Directory Structure
```text
ucsd_robocar_nav2_pkg/
├── launch/
│   └── all_components.launch.py       # Main launch file that starts all nodes
├── config/
│   ├── car_config.yaml                # Enable/disable sensors and nodes
│   └── pkg_locations_ucsd.yaml        # Maps packages to launch files, topics
├── setup.py                           # Python package setup
├── cone_detection_node.py             # Cone detection using OAK-D
├── lidar_processor_node.py            # LiDAR data processing
├── behavior_node.py                   # High-level behavior logic
├── stop_line_detector.py              # Stop line detection

