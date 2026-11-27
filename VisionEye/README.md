# VisionEye Object Mapping Using YOLO

## Project Overview
This project demonstrates object detection and VisionEye object mapping using the Ultralytics YOLO framework.

The main objective is to detect objects in a traffic video and visualize their spatial relationship with a predefined observation point using VisionEye.

The project uses OpenCV for video processing and Ultralytics solutions for object detection, tracking, and visualization.

## Technologies Used
- **Python**
- **OpenCV:** Used to load, read, and process video frames.
- **Ultralytics YOLO:** Used for object detection.
- **VisionEye:** Used to visualize the relationship between detected objects and a fixed observation point.
- **FFmpeg:** Used to compress the processed video.

## Input Video
The input video contains a traffic scene with different road users and traffic elements, including:
- People
- Cars
- Motorcycles
- Buses
- Traffic lights

**Video Properties:**
- Resolution: 1080 × 1920
- Frame Rate: 60 FPS
- Total Frames: 958
- Duration: Approximately 16 seconds

## YOLO Model
The project uses the pretrained **YOLO11n (Nano)** model.

YOLO11n was selected because it provides a lightweight and efficient solution for object detection while maintaining good detection performance.

## Selected Classes
The model is configured to detect only the following COCO classes:

| Class ID | Object |
|---|---|
| 0 | Person |
| 2 | Car |
| 3 | Motorcycle |
| 5 | Bus |
| 9 | Traffic Light |

Class filtering helps focus on relevant traffic objects, reduces unnecessary detections, and improves visualization clarity.

*Note: Road surfaces are not included because they are not a separate object class in the standard COCO dataset.*

## VisionEye Configuration
VisionEye is initialized using the YOLO11n model and the selected classes.

The observation point is defined as:

`vision_point = (540, 1800)`

This point is located near the bottom-center of the video frame.

VisionEye draws mapping lines between this fixed point and detected objects, making their spatial relationship easier to visualize.

## Implementation Steps

### Step 1: Environment Preparation
Install and import the required libraries, including Ultralytics and OpenCV.

### Step 2: Load the Input Video
Open the traffic video using OpenCV and extract its properties, including frame width, frame height, FPS, and total frame count.

### Step 3: Initialize VisionEye
Load the pretrained YOLO11n model, select the required object classes, and define the observation point.

### Step 4: Process Video Frames
Process the video frame by frame:
1. Read each frame using OpenCV.
2. Apply the VisionEye solution.
3. Detect and track the selected objects.
4. Draw bounding boxes, labels, and mapping lines.
5. Write the processed frames into a new output video.

### Step 5: Save the Output
Save the processed video and compress it into MP4 format using H.264 encoding to reduce its file size while maintaining reasonable visual quality.

## Output
The final processed video demonstrates:
- Detected objects with bounding boxes and labels.
- VisionEye mapping lines connecting the observation point to detected objects.
- A complete processed traffic video.

**Output File:** `VisionEye_compressed.mp4`

## Project Files
- `VisionEye_Object_Mapping.ipynb` – Jupyter Notebook containing the complete implementation and explanations.
- `VisionEye_compressed.mp4` – Compressed output video.
- `README.md` – Project documentation.

## Conclusion
This project demonstrates how YOLO object detection can be combined with VisionEye visualization to analyze traffic scenes from a predefined observation point.

The implementation provides a visual representation of detected objects and their spatial relationship with the observation point, which can be useful in visual monitoring and traffic analysis.