# Real-Time Lane Detection on macOS

## Requirements
- Python 3.11
- OpenCV
- NumPy
- PyTorch
- YOLOv5

## Setup

Create and activate a virtual environment:

    python3.11 -m venv .venv
    source .venv/bin/activate

Install the libraries:

    python -m pip install --upgrade pip
    python -m pip install numpy==1.26.4 opencv-python==4.10.0.84
    python -m pip install torch==2.5.1 torchvision==0.20.1
    python -m pip install matplotlib pandas PyYAML requests scipy tqdm Pillow seaborn tensorboard thop

## Run lane detection

    python lane.py

This generates lines.avi.

## Run object detection

    python yolov5/detect.py --weights yolov5/yolov5s.pt --source lines.avi --view-img --device cpu

The annotated video is saved under:

    yolov5/runs/detect/

## Pipeline

1. OpenCV processes the video and detects road lane boundaries.
2. YOLOv5 detects objects such as cars, people and traffic lights.
3. The final annotated video combines the results.

Tested on macOS with Python 3.11.9.
