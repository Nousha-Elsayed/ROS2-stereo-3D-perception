# Stereo 3D Perception using ROS2

This repository implements a real-time stereo vision perception pipeline in ROS2 for 3D depth estimation and target detection.

The system processes synchronized stereo camera streams to compute disparity and estimate depth, while integrating a custom-trained YOLO model to detect and localize objects such as balls and goals in 3D space.

## Features
- Stereo image rectification and calibration
- Real-time depth estimation using disparity maps
- YOLO-based object detection (ball & goal)
- 3D distance estimation of detected targets
- ROS2 modular node architecture

## Architecture
The system follows a full stereo pipeline:
Stereo Camera → Rectification → Disparity → Depth → YOLO Detection → 3D Localization

## Topics
- `/stereo/left/image_rect_color`
- `/stereo/right/image_rect_color`
- `/stereo/disparity`
- `/ball/depth`

## Model Performance
- mAP@50: ~0.97
- Real-time inference (~5.7 ms per image)
