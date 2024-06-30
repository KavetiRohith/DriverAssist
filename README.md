# DriverAssist

## Lane and Stop Sign Detection

This project provides a C++ implementation for detecting lanes and stop signs in a video using OpenCV and a custom channel implementation for inter-thread communication.

## Features

- **Lane Detection**: Detects and highlights lanes on the road using the Hough Line Transform.
- **Stop Sign Detection**: Detects stop signs using a pre-trained Haar Cascade Classifier.
- **Multithreading**: Uses custom `Channel` and `BufferedChannel` classes for inter-thread communication to efficiently process video frames in parallel.

## Code Overview

### `channel.h`

Defines `Channel` and `BufferedChannel` classes for thread-safe communication.

- **Channel**: A simple unbuffered channel for single-item communication.
- **BufferedChannel**: A buffered channel that can hold multiple items.

### `main.cpp`

- Loads video frames.
- Processes frames for lane and stop sign detection.
- Uses multithreading for efficient processing.

#### Functions

- **frameLoader**: Loads frames from the video and sends them through a `BufferedChannel`.
- **processStopSigns**: Detects stop signs in a given frame.
- **processLanes**: Detects lanes in a given frame and calculates the offset from the lane center.

## Configuration

Several preprocessor directives control the behavior of the application:

- **DEBUG**: Enable to draw detected lanes on the frames.
- **OUTPUT_VIDEO**: Enable to save the processed video.
- **OUTPUT_FRAMES**: Enable to save individual frames.
- **RESIZE**: Enable to resize frames for faster processing.
- **SHOW_ROI**: Enable to show the region of interest.
