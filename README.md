# FitNessy

A real-time computer vision fitness application that detects your body joints through your webcam, computes joint angles, and automatically counts your exercise repetitions — no wearables needed.

Built as a group school project to practice **object-oriented programming** in Python.

---

## Quick start

> **Requirements:** a webcam and Python 3.11+

### Step 1 — Install `uv`

`uv` is the package manager used by this project. Pick the command for your OS:

**macOS / Linux:**
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Windows (PowerShell):**
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

> After installation, restart your terminal so `uv` is available in your PATH.

### Step 2 — Clone the repository

```bash
git clone git@github.com:PaulineF38/FitNessy.git
cd FitNessy
```

### Step 3 — Install dependencies

```bash
uv sync
```

This creates a virtual environment and installs all dependencies automatically.

### Step 4 — Launch the app

```bash
uv run python -m fitness.app
```

A window opens. Click **"Choisir Niveau!"**, pick your difficulty, and start your workout. Press `q` at any time to exit.

---

## About the project

FitNessy uses **Google MediaPipe** to detect 33 body landmarks in real time from your webcam feed. From those landmarks, the app computes joint angles frame by frame to determine your position and count how many times you complete a movement.

The codebase is structured around OOP principles: each exercise has its own detector class that inherits from a shared base class (`Detector → PoseDetector → SquatDetector`, etc.), making the code modular and easy to extend with new exercises.

### Exercises supported

| Exercise | Detection method |
|---|---|
| Push-ups | Elbow angle |
| Squats | Knee angle |
| Heel-to-buttocks | Knee flexion |
| Knee raises | Hip & knee angle |
| Plank | Body alignment |
| Tree pose | Balance & leg angle |
| Cobra (yoga) | Spine extension |
| Meditation pose | Body symmetry |

### Difficulty levels

Choose between **Easy**, **Medium**, and **Hard** — each level unlocks more exercises and increases the target rep count.

### Tech stack

| Library | Role |
|---|---|
| [MediaPipe](https://google.github.io/mediapipe/) | Real-time body landmark detection |
| [OpenCV](https://opencv.org/) | Webcam capture & UI rendering |
| [scikit-learn](https://scikit-learn.org/) / [Keras](https://keras.io/) | ML model for rep classification |
| [uv](https://docs.astral.sh/uv/) | Python dependency management |

---

*Group school project — 2024/2025*
