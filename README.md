# Real-Time Lane Detection using OpenCV and YOLOv5

A computer vision project that combines traditional image processing with deep learning to detect road lane boundaries and identify objects in road videos.

## Features

- Road lane detection using OpenCV.
- Gaussian blur for noise reduction.
- Canny edge detection and Region of Interest (ROI) masking.
- Hough Line Transform for lane-line detection.
- YOLOv5 object detection for cars, people, traffic lights, and other supported classes.
- Annotated video output.

## Technology Stack

- Python 3.11
- OpenCV
- NumPy
- PyTorch
- YOLOv5

## How It Works

1. Read the input road video.
2. Process video frames to detect lane boundaries.
3. Generate a lane-annotated video named `lines.avi`.
4. Pass the processed video to YOLOv5.
5. Save the final video with object-detection labels and bounding boxes.

## Installation on macOS

### 1. Clone the repository

    git clone https://github.com/piyushnerkarEX/Real-Time-Lane-Detection.git
    cd Real-Time-Lane-Detection

### 2. Create a virtual environment

    python3.11 -m venv .venv
    source .venv/bin/activate
    python -m pip install --upgrade pip

### 3. Install dependencies

    python -m pip install numpy==1.26.4 opencv-python==4.10.0.84
    python -m pip install torch==2.5.1 torchvision==0.20.1
    python -m pip install matplotlib pandas PyYAML requests scipy tqdm Pillow seaborn tensorboard thop

## Running the Project

### Stage 1: Lane Detection

    python lane.py

This processes the configured input video and generates `lines.avi`.

### Stage 2: Object Detection

    python yolov5/detect.py --weights yolov5/yolov5s.pt --source lines.avi --view-img --device cpu

The annotated video is saved under `yolov5/runs/detect/`. For example:

`yolov5/runs/detect/exp/lines.mp4`

The output folder name may change on subsequent runs.

## Project Structure

    Real-Time-Lane-Detection/
    ├── lane.py
    ├── video.m4v
    ├── yolov5/
    ├── results/
    ├── README.md
    ├── README-MAC.md
    └── LICENSE

## Limitations

- Performance may decrease in poor lighting, shadows, or unclear lane markings.
- Traditional lane detection may struggle with sharp curves and complex road conditions.
- The project is an educational computer vision demonstration, not a production-ready autonomous driving system.

## Credits

Original project: [Nirmal-C/Real-Time-Lane-Detection](https://github.com/Nirmal-C/Real-Time-Lane-Detection)

Object detection: [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5)

Refer to the included LICENSE file for licensing information.
