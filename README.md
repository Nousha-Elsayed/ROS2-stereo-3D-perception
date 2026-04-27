# Stereo 3D Perception using ROS2

This repository implements a real-time stereo vision perception pipeline in ROS2 for 3D object detection and depth estimation.

The system uses synchronized stereo camera streams processed through the ROS2 `stereo_image_proc` pipeline to generate disparity maps, which are then used to compute depth information. A custom-trained YOLO model is integrated to detect objects such as balls and goals in the stereo camera view.

The combination of stereo disparity-based depth estimation and object detection enables real-time 3D perception for robotics applications.

---

## Features
- Stereo camera calibration and image rectification
- Real-time disparity map generation (ROS2 stereo_image_proc)
- Depth estimation from stereo disparity
- YOLO-based object detection (ball & goal)
- Fusion-ready pipeline for 3D localization
- Modular ROS2 architecture

---

## System Pipeline

Stereo Camera → Rectification → Disparity → Depth → YOLO Detection → 3D Localization

---

## ROS2 Topics
- `/stereo/left/image_rect_color`
- `/stereo/right/image_rect_color`
- `/stereo/left/camera_info`
- `/stereo/right/camera_info`
- `/stereo/disparity`
- `/stereo/points2`

---

## Depth Computation

Depth is calculated from stereo disparity using:

z = (f · B) / d

Where:
- z = depth (distance to object)
- f = focal length
- B = stereo baseline
- d = disparity value

---

## Model Performance
- mAP@50: ~0.97
- Real-time inference: ~5.7 ms per image
- Custom YOLO model trained on ball & goal dataset

---

## Notes
- Disparity is generated using ROS2 `stereo_image_proc`
- Depth is derived from disparity values
- YOLO detections can be fused with depth for 3D object localization

---

## Future Work
- Improve YOLO-depth fusion accuracy
- Real-time 3D bounding box estimation
- Trajectory tracking of detected objects in 3D space
