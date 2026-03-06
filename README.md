# Drowsiness Detection System (Project #11)

The eleventh project in my **AI/ML Learning Path**. This project focuses on **Safety-focused Computer Vision**, using facial landmark detection to monitor driver alertness and detect signs of fatigue in real-time.

## 📌 Overview
This system uses a webcam to track the user's eyes and calculates the **Eye Aspect Ratio (EAR)**. If the EAR remains below a certain threshold for a predefined duration, the system identifies the user as drowsy and triggers an alert.

## 🛠️ Tech Stack
* **Language:** Python
* **Library:** Dlib (68-point landmark predictor)
* **Computer Vision:** OpenCV
* **Mathematics:** SciPy (Euclidean distance)
* **Logic:** Eye Aspect Ratio (EAR) algorithm

## ⚙️ How It Works
1. **Face Detection:** Uses Dlib's HOG-based face detector to locate the face.
2. **Landmark Prediction:** Identifies the 68 specific points on the face, specifically focusing on the coordinates of the eyes (points 36 to 47).
3. **EAR Calculation:** For each eye, the ratio of the eye's height to its width is calculated using the formula:
   $EAR = \frac{||p2 - p6|| + ||p3 - p5||}{2||p1 - p4||}$
4. **Monitoring:** - **Blink:** A temporary drop in EAR.
    - **Drowsiness:** If EAR stays low for more than $N$ consecutive frames, an alarm is triggered.

## 🚀 Quick Start
1. **Install Dependencies:**
   ```bash
   pip install opencv-python dlib scipy imutils
2. **Download Model:**
    Download the ```shape_predictor_68_face_landmarks.dat``` file and place it in the project directory.
3. **Run the Script:**
   ```bash
   python main.py --shape-predictor shape_predictor_68_face_landmarks.dat

*Progress: Successfully applied facial landmark geometry to solve real-world safety problems.*
