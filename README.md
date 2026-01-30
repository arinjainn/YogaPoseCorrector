# Yoga Pose Corrector

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?style=for-the-badge&logo=opencv&logoColor=white)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Pose%20Estimation-orange?style=for-the-badge)

Ever tried practicing yoga alone and wondered, *"Am I even doing this right?"* I built **Yoga Pose Corrector** to solve that. It’s a computer vision tool that acts like a supportive gym buddy. It watches your form in real-time through your webcam, calculates your joint angles, and gives you instant, specific feedback (like "Straighten your leg!") so you can improve your posture safely.

---

## 📸 Demo

<p align="center">
  Here is the system in action. It detects key body points and instantly categorizes your form as "Fighting" (needs work) or "Perfect".
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

It’s not magic, it’s geometry! Here is the breakdown:

1.  **It Sees You:** Using **MediaPipe**, the code finds 33 specific points on your body (shoulders, hips, knees, etc.) from the video feed.
2.  **It Measures You:** It calculates the geometric angles between these points. For example, to check if your arm is straight, it measures the angle at your elbow.
3.  **It Coaches You:** We compare your angles against "Gold Standard" ranges. If your knee is bent at 140° but needs to be 180°, the program flags it and tells you exactly how to fix it.

## ✨ Key Features

* **Runs on your Laptop:** No expensive GPU needed. I optimized this to run smoothly on standard CPUs.
* **Privacy First:** Everything runs locally on your machine. No video of you is ever sent to the cloud.
* **Visual Feedback:** The skeleton overlay turns Green when you are correct and Red when you need to adjust.
* **Current Poses:** Supports *Tree Pose*, *Warrior II*, and *T-Pose* calibration.

## 🛠️ Tech Stack

* **Python** (The logic)
* **OpenCV** (The eyes)
* **MediaPipe** (The brain/pose estimation)
* **NumPy** (The math)

## ⚡ Getting Started

### Prerequisites

You just need Python installed. I recommend using a virtual environment so things stay clean.

### Installation

```bash
# 1. Clone the repo
git clone [https://github.com/arinjainn/YogaPoseCorrector.git](https://github.com/arinjainn/YogaPoseCorrector.git)

# 2. Enter the directory
cd YogaPoseCorrector

# 3. Install dependencies
pip install -r requirements.txt
