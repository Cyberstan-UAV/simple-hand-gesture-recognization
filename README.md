 simple-hand-gesture-recognization
an simple hand gestrure  recognization using Python | OpenCV | MediaPipe | pyautogui | math | cvzone


 Hand Gesture-Based PC Control System

This project is a proof-of-concept touchless Human-Computer Interaction (HCI) system that enables users to control a computer using only hand gestures captured through a webcam. Built using Python, OpenCV, and MediaPipe, this system offers real-time hand tracking, gesture recognition, and control mappings such as cursor movement and system volume adjustment.

---

 Project Overview

Traditional computer input methods (like keyboards, mice, or touch) can be limiting in certain contexts. With the rise of AI-powered computer vision, touchless interfaces are becoming increasingly feasible — especially for accessibility applications, smart environments, and AR/VR systems.

This project explores one such interaction method: controlling a PC with your bare hands via a webcam.

---

Features

1. Real-Time Hand Tracking
- Utilizes **MediaPipe Hands** to detect and track 21 3D landmarks on each hand
- Works with a standard laptop or USB webcam

 2. Cursor Control
- Detects when the palm is open
- Maps hand movement within a region of interest (ROI) to screen resolution using interpolation
- Moves the mouse cursor in real-time based on the position of the hand

3. Click Detection (Optional Extension)
- Click or drag detection based on finger distance or pinch gestures
- Can be further trained with custom gesture models

4. Volume Control
- Calculates the distance between the **thumb tip** and **index finger tip**
- Converts distance to system volume level using mathematical scaling
- Can be integrated with `pycaw` for more accurate volume control

---

Tech Stack

- Language: Python 3.x
- Libraries:
  - OpenCV
  - MediaPipe
  - PyAutoGUI
  - Math
  - Numpy
  - Cvzone (optional wrapper for easier visualization)

---

 Technical Insights

- Coordinate Mapping: Hand landmark coordinates (from webcam) are normalized and then interpolated to match screen resolution using `numpy.interp`.
- Performance Considerations:  
  - FPS drops observed due to sequential frame capture and processing  
  - Mouse movement lag traced back to frame delay and lack of multithreading  
  - Improvements possible through threaded frame grabbing or use of multiprocessing  
- Gesture Logic:  
  - Distance between specific landmarks is used to define gestures  
  - Hand openness, angle, or finger state combinations can be used to expand gesture set

---

 Requirements

- Python 3.7+
- Webcam (built-in or external)
- A reasonably powerful CPU (GPU not mandatory but helps With Better FPS and smoother operation)
- Windows OS (for PyAutoGUI and screen control functions — Linux/Mac support may need tweaks)

---

 Known Limitations

- Low FPS and lag on older or low-spec systems
- Not yet optimized with multithreading
- Basic gestures only — not trained with a custom model
- Only supports single-hand tracking in this version

---

Future Improvements

- Add multithreading to increase frame processing speed
- Integrate deep learning for dynamic gesture classification
- Support multi-hand gestures and left/right hand detection
- Deploy on edge devices like Raspberry Pi or Jetson Nano
- Combine with voice control for hybrid HCI system

---

 Author

Piyush Dangare  
Third-Year B.E. (E&TC) Student | Aspiring Defense & Aerospace Innovator  
Passionate about embedded systems, AI, and building real-world tech  
[LinkedIn Profile](www.linkedin.com/in/piyush-dangare-555933358)

---

 License

This project is open-source under the MIT License. See the `LICENSE` file for more details.

---

 Contributions

Pull requests, feedback, and forks are welcome. If you'd like to improve performance or add more gestures, feel free to open an issue or submit a PR.







