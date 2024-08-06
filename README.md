# Visual traffic monitoring
 
## Overview
The goal of this project is to develop an automatic system for video analysis that enables
visual traffic monitoring at a road intersection. The system gets as input data
the video stream from a static camera and should be able to: 

a) classify road lanes as being
occupied or not given a video frame; 

b) track a specific vehicle in a given video;

## Key Features
Task 1: Vehicle Detection
 - Algorithm: Utilizes YOLOv4-p6 for high-accuracy vehicle detection.
 - Image Preprocessing: Implements OpenCV's cv.dnn.blobFromImage for image scaling and channel reordering.
 - Lane Detection: Uses cv.polyline to define lanes and cv.pointPolygonTest to identify vehicle presence in specific lanes.
 - Error Handling: Refines detection algorithms for lanes with higher error rates by focusing on specific vehicle regions.
   
Task 2: Vehicle Tracking
 - Algorithm: Employs the DaSiamRPN tracker from OpenCV for real-time vehicle tracking in video footage.
 - Tracking Process: Initializes the tracker with a bounding box, updates frames, and stores tracking data.
 - Output: Produces text files with tracking results for each video, capturing the vehicle's location throughout the sequence.

## Requirements
Libraries:
 - numpy: 1.24.3
 - opencv: 4.7.0
 - pip: 23.1.2
 - python: 3.11.4

## Project Files
Task 1 Script: project2_task1.ipynb
 - Function: solve_all_images(images_path, queries_path, drawned_lanes)
 - Dependencies: yolov4-p6.cfg, yolov4-p6.weights, coco.names
 - Output Folder: results_task1
 - Example: solve_all_images("train/Task1","train/Task1", drawned_lanes)

Task 2 Script: project2_task2.ipynb
 - Function: solve_all_images(videos_path, text_files_path)
 - Dependencies: dasiamrpn_kernel_cls1.onnx, dasiamrpn_kernel_r1.onnx, dasiamrpn_model.onnx
 - Output Folder: results_task2
 - Example: solve_all_videos("train/Task2","train/Task2")
