# 🎯 Feature-Based Object Tracking

Real-time object tracking pipeline using **Harris Corner Detection** and **Lucas–Kanade Optical Flow**. Detects stable corner features in a user-selected region and tracks them across video frames using sparse optical flow.

---

## 📌 Overview

This project implements a feature-based object tracking system built with Python and OpenCV. The user selects an object in the first frame via a bounding box, and the system automatically detects strong corner features inside that region and tracks them throughout the video sequence.

---

## ⚙️ How It Works

1. Load video and let user define a bounding box around the object
2. Detect strong corner features inside the region using Harris Corner Detection
3. Track those features across frames using Lucas–Kanade Optical Flow
4. Filter out unstable/lost points
5. Recompute bounding box from remaining tracked points
6. Repeat for every frame

---

## 🧠 Algorithms

| Algorithm | Purpose |
|---|---|
| Harris Corner Detection | Identifies strong, stable feature points inside the object region |
| Lucas–Kanade Optical Flow | Estimates motion of feature points between consecutive frames |

**Harris Corner Response:**
```
R = det(M) - k * (trace(M))²
```

**Optical Flow Constraint:**
```
Ix·u + Iy·v + It = 0
```

---

## 🛠️ Tech Stack

- Python
- OpenCV
- NumPy
- Matplotlib
- Google Colab

---

## 📁 Project Structure

```
📁 object-tracking/
├── Object_Tracking_Report.docx   
├── object_tracking.py                 
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install opencv-python numpy matplotlib
```

### Run
```bash
python object_tracking.py
```

> **Note:** The project was developed and tested on **Google Colab**. `cv2.imshow()` and `cv2.selectROI()` are not supported in Colab — Matplotlib is used for visualization and the bounding box is set manually in the code.

---

## ✅ Results

The system performed well under:
- Slow to moderate object motion
- Small illumination changes
- Partial occlusion

Performance degraded under:
- Very fast motion
- Severe occlusion
- Complete feature point loss

---

## ⚠️ Limitations

- Requires manual object initialization
- Not scale invariant
- Sensitive to large, abrupt motion


---

## 📄 Report

Full project report is available in [`docs/Object_Tracking_Report.docx`](docs/Object_Tracking_Report.docx)

---

## 👤 Author

**Muhammad Zaid** — 23L-2582  
BS Data Science, FAST-NUCES Lahore
