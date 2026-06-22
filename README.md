# Yoga Pose Corrector

A computer vision project that watches your yoga pose through a webcam and tells you what to fix. Built with OpenCV and MediaPipe — it tracks 33 body landmarks, calculates joint angles, and compares them against a target pose in real time.

I started this because I kept practicing yoga alone with no idea if my form was actually right.

## Demo

![demo](PASTE_YOUR_DEMO_GIF_URL_HERE)

Runs locally against your webcam — OpenCV opens a native window, so this isn't a hosted web app right now. See below for how to run it yourself.

### Screenshots

| | |
|---|---|
| ![Standard Pose Analysis](https://github.com/user-attachments/assets/24e74b56-0494-47fc-821b-3f74adcdf90b) | ![Warrior Pose](https://github.com/user-attachments/assets/a2deccfe-5961-4f39-ac83-f9ece341e13d) |
| Standard pose analysis | Warrior II (wide stance) |
| ![Tree Pose Leg](https://github.com/user-attachments/assets/97a60cc7-558b-49c6-aff8-00d3f8f58b4f) | ![Tree Pose Upper Body](https://github.com/user-attachments/assets/551fbe82-c12f-439a-bc55-1de2d327d04f) |
| Tree pose, leg correction | Tree pose, upper body |
| ![Standing Posture](https://github.com/user-attachments/assets/5aa299b0-cc5f-49ac-b1dd-a85ae422cbd5) | ![T Pose Calibration](https://github.com/user-attachments/assets/6ef5b5fa-5442-4007-aae2-1cc82159adc8) |
| Standing posture check | T-pose calibration |

## How it works

MediaPipe finds 33 landmarks on your body from the webcam feed (shoulders, elbows, hips, knees, etc). From those landmarks I calculate the angle at each major joint using basic trig (`arctan2` between three points).

Those angles get compared against a target pose image. If your knee angle is 140° and the target wants 180°, it flags it and draws a red circle on that joint with text telling you what to fix ("Extend the right arm at elbow", etc).

There are two scoring methods running together: cosine similarity across all landmark positions, and average angular deviation across the 8 tracked joints. Whichever score is lower becomes your live accuracy percentage.

Pose classification (Tree Pose, Warrior II, T-Pose) works by checking which combination of joint angles falls within a hardcoded range for that pose.

## Tech stack

Python, OpenCV, MediaPipe, NumPy, SciPy, Pandas.

## Running it

You need Python 3.8+ and a webcam.

```bash
git clone https://github.com/arinjainn/YogaPoseCorrector.git
cd YogaPoseCorrector

python3 -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

pip install -r requirements.txt
```

Then open `pose-final.ipynb` and run all cells. Two windows will open: `target` (the reference pose image) and `MediaPipe Feed` (your live webcam feed with the skeleton overlay and feedback text). Press `q` to quit.

The default target is `Images/yoga25.jpg`. You can change the `path` variable in the last cell to try other poses from `Images/poses/`.

## Known limitations

- Desktop-only right now — needs a webcam and a display, won't run on a server or in a browser as-is.
- Only classifies three poses (Tree, Warrior II, T-Pose); anything else just shows as a score against whatever target image you pick.
- Angle thresholds are hardcoded, not learned, so accuracy varies by body type and camera angle.

## What I'd do next

Porting the pose detection to MediaPipe's JS version would make this run entirely in-browser, which would actually make it deployable as a live site instead of a local script. That's the next thing I'd build if I kept going.

## License

MIT (or pick whichever you want).
