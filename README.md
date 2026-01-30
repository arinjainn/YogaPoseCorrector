# Yoga Pose Corrector

A computer vision application that utilizes MediaPipe and OpenCV to detect yoga poses in real-time. The system analyzes body landmarks to calculate joint angles and provides immediate feedback on posture accuracy.

## Overview

This project is designed to assist users in practicing yoga by verifying their form against geometric heuristics. It processes video input (webcam or video file) to track 33 key body landmarks. The core logic calculates specific angles (e.g., hip-knee-ankle, shoulder-elbow-wrist) to determine if a pose is being held correctly.

## Features

- **Real-time Pose Estimation:** Leverages MediaPipe's Blazepose model for high-performance landmark tracking.
- **Geometric Angle Calculation:** Computes precise angles between joints to assess pose validity.
- **Visual Feedback System:** Draws skeleton overlays and displays live angle data directly on the video feed.
- **Correction Mechanism:** Alerts the user if their posture deviates from the defined threshold (e.g., "Straighten Leg").
- **Privacy-Centric:** All processing occurs locally on the CPU/GPU; no data is transmitted externally.

## Tech Stack

- **Python 3.x**
- **MediaPipe** (Pose estimation)
- **OpenCV** (Image processing and video capture)
- **NumPy** (Trigonometric calculations)

## Installation

1. **Clone the repository**
   ```bash
   git clone [https://github.com/arinjainn/YogaPoseCorrector.git](https://github.com/arinjainn/YogaPoseCorrector.git)
   cd YogaPoseCorrector
