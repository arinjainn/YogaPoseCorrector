# Yoga Pose Corrector

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?style=for-the-badge&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Pose%20Estimation-orange?style=for-the-badge)


A real-time computer vision application that helps users maintain correct yoga posture. It acts as a virtual trainer by detecting body landmarks and calculating joint angles to provide instant feedback (e.g., "Straighten your knee").

Built to explore the practical applications of **MediaPipe** in health and fitness tech.

---
## 📸 Demo

<p align="center">
  Real-time analysis and feedback: The system detects key landmarks and calculates joint angles to categorize posture as "Fighting" (incorrect) or "Perfect".
</p>

<table align="center">
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/24e74b56-0494-47fc-821b-3f74adcdf90b" width="100%" />
      <br />
      <b>Standard Pose Analysis</b>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/a2deccfe-5961-4f39-ac83-f9ece341e13d" width="100%" />
      <br />
      <b>Warrior Pose (Wide Stance)</b>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/97a60cc7-558b-49c6-aff8-00d3f8f58b4f" width="100%" />
      <br />
      <b>Tree Pose (Leg Correction)</b>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/551fbe82-c12f-439a-bc55-1de2d327d04f" width="100%" />
      <br />
      <b>Tree Pose (Upper Body)</b>
    </td>
  </tr>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/5aa299b0-cc5f-49ac-b1dd-a85ae422cbd5" width="100%" />
      <br />
      <b>Standing Posture Check</b>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/6ef5b5fa-5442-4007-aae2-1cc82159adc8" width="100%" />
      <br />
      <b>T-Pose / Calibration</b>
    </td>
  </tr>
</table>


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
