# Yoga Pose Corrector

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?style=for-the-badge&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Pose%20Estimation-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

A real-time computer vision application that helps users maintain correct yoga posture. It acts as a virtual trainer by detecting body landmarks and calculating joint angles to provide instant feedback (e.g., "Straighten your knee").

Built to explore the practical applications of **MediaPipe** in health and fitness tech.

---

## 📸 Demo

> *[Insert a GIF or Screenshot of your project running here. Seeing the skeleton overlay in action makes a huge difference!]*

## 🚀 How It Works

The core of this application relies on vector geometry and thresholding:

1.  **Landmark Detection:** Uses the MediaPipe Blazepose model to extract 33 distinct $(x, y)$ coordinates for the user's body.
2.  **Angle Calculation:** It calculates the angle between three distinct keypoints (e.g., Hip $\rightarrow$ Knee $\rightarrow$ Ankle) using trigonometric functions (`atan2`).
3.  **Heuristic Logic:** The calculated angles are compared against a dataset of "correct" pose ranges. If the user falls outside these ranges, the UI flags the specific error.

## ✨ Features

* **Zero Latency:** Optimized for real-time performance on standard CPU hardware.
* **Privacy Focused:** No video data is sent to the cloud; everything runs locally.
* **Visual Feedback:** Dynamic skeleton overlay that changes color based on pose accuracy.
* **Pose Library:** (Currently supports: *Tree Pose*, *Warrior II*, *Plank*) - *[Edit this list based on your actual code]*

## 🛠️ Tech Stack

* **Language:** Python
* **Core Libraries:** `opencv-python`, `mediapipe`, `numpy`
* **Math:** Trigonometry for vector angle calculation

## ⚡ Getting Started

### Prerequisites

Make sure you have Python installed. It is recommended to use a virtual environment.

### Installation

```bash
# 1. Clone the repo
git clone [https://github.com/arinjainn/YogaPoseCorrector.git](https://github.com/arinjainn/YogaPoseCorrector.git)

# 2. Enter the directory
cd YogaPoseCorrector

# 3. Install dependencies
pip install -r requirements.txt
