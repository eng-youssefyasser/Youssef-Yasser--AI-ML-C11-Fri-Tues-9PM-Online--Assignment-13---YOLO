# YOLO Object Counting in Video

## Project Overview

This project implements an object detection, tracking, and counting system using **YOLO and OpenCV**.

The system processes a traffic video frame by frame, detects vehicles and other objects, tracks their movement, and counts objects crossing a predefined virtual line.

This type of system can be used in:
- Traffic monitoring.
- Vehicle counting.
- People counting.
- Smart city applications.
- Surveillance systems.

## Technologies Used

- **Python:** Main programming language.
- **Ultralytics YOLO:** Object detection and tracking.
- **OpenCV:** Video reading, frame processing, and output video writing.
- **Matplotlib:** Displaying video frames.
- **Kaggle Notebook:** Development and execution environment.

## Project Workflow

### Step 1: Prepare the Environment

The required libraries are imported and prepared:

- Ultralytics
- OpenCV
- YOLO pretrained model
- Ultralytics ObjectCounter

OpenCV is used to handle video input, process frames, and save the final output.

### Step 2: Load a Pretrained YOLO Model

A pretrained YOLO nano model (`yolo11n.pt`) is loaded.

Pretrained models have already learned to recognize objects from previously collected datasets.

The COCO pretrained model supports common object classes, including:

| Class ID | Object |
|---|---|
| 0 | Person |
| 1 | Bicycle |
| 2 | Car |
| 3 | Motorcycle |
| 5 | Bus |
| 7 | Truck |

These classes are selected for traffic and object counting.

### Step 3: Load the Input Video

The input traffic video is loaded using OpenCV.

**Video Properties:**

| Property | Value |
|---|---:|
| Width | 1080 pixels |
| Height | 1920 pixels |
| FPS | 60 |
| Total Frames | 958 |
| Duration | Approximately 15.97 seconds |

FPS represents the number of frames displayed per second.

Video dimensions are required to configure the output video writer correctly.

### Step 4: Define the Counting Line

A virtual counting line is defined using two coordinates:

- Point 1: `(280, 1200)`
- Point 2: `(900, 1200)`

The line is positioned across the road to detect objects crossing it.

The position of the line is important because it directly affects the counting results.

### Step 5: Track and Count Objects

Ultralytics ObjectCounter is used to perform object detection, tracking, and counting.

The system processes the video frame by frame:

1. Read a video frame using OpenCV.
2. Detect objects using YOLO.
3. Track objects across consecutive frames.
4. Assign and maintain object IDs.
5. Count objects crossing the defined line.
6. Draw detection and counting information on the processed frame.

Object IDs help prevent the same tracked object from being counted repeatedly.

The ObjectCounter solution handles the tracking and counting operations internally.

### Step 6: Save the Output Video

The processed frames are saved into a new video using OpenCV VideoWriter.

The final output is saved in AVI format using the MJPG codec.

**Output file:** `Traffic_counted.avi`

The processed video displays:
- Detected objects.
- Bounding boxes.
- Object tracking information.
- The counting line.
- IN and OUT counting results.

## Final Results

The system provides two counting results:

- **IN Count:** Number of objects crossing the line in one direction.
- **OUT Count:** Number of objects crossing the line in the opposite direction.

The total number of counted crossings is calculated as:

`Total Count = IN Count + OUT Count`

The final numerical results are displayed in the Kaggle Notebook after video processing.

## Project Files

| File | Description |
|---|---|
| `Traffic.mp4` | Original input video |
| `Traffic_counted.avi` | Processed output video |
| `yolo11n.pt` | Pretrained YOLO nano model |

## Conclusion

This project demonstrates how computer vision techniques can be used for real-time object detection, tracking, and counting in video streams.

By combining YOLO, OpenCV, and Ultralytics ObjectCounter, the system can identify objects, follow their movement, and count their crossings over a predefined line.

The project provides a practical example of how AI-powered computer vision can be applied to traffic monitoring and intelligent surveillance systems.