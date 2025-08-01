# Vehicle Detection and Counting with YOLOv8

This project implements real-time vehicle detection, tracking, and counting using the YOLOv8 object detection model and the SORT tracking algorithm. The system is optimized with CUDA and cuDNN for high-performance inference on GPU.

## Features

* Object detection using YOLOv8 (`yolov8l.pt`)
* Object tracking with SORT (Simple Online and Realtime Tracking)
* Region-of-interest masking to limit detection area
* Line-based vehicle counting with unique ID tracking
* Support for real-time processing via GPU acceleration

## Requirements

* Python 3.8+
* CUDA-compatible GPU with cuDNN installed
* Python packages:

  ```bash
  pip install ultralytics opencv-python cvzone numpy
  ```

## File Overview

* `main.py`: Core detection and tracking script
* `mask.png`: Binary mask to define detection region
* `graphics.png`: Optional overlay graphics for UI
* `sort.py`: SORT tracker implementation
* `Videos/cars.mp4`: Sample input video
* `Yolo-Weights/yolov8l.pt`: YOLOv8 pre-trained model weights

## How It Works

1. Video frames are read and masked to focus on a region of interest.
2. YOLOv8 detects objects in the masked area.
3. Only relevant vehicle classes (`car`, `truck`, `bus`, `motorbike`) are retained.
4. SORT tracks detected objects across frames using Kalman filtering and ID assignment.
5. Vehicles crossing a predefined line are counted once per unique ID.

## Customization

* Modify the `limits` variable in `car-counter.py` to adjust the counting line.
* Replace `mask.png` to change the detection region.
* Use the video car.mp4 for this model.
* Use different YOLOv8 model sizes (e.g., `yolov8n.pt`, `yolov8s.pt`) depending on performance needs.

## License

This project is released under the MIT License.


