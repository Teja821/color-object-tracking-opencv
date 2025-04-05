# 🎯 Color Object Tracking with OpenCV

This project demonstrates real-time **multi-color object tracking** using OpenCV and Python. It captures video from your webcam and detects specific colors in real-time using the HSV color space.

---

## 🚀 Features

- 🎨 Detect and track multiple colored objects in real-time
- 🔧 Adjustable HSV color range using trackbars
- 🧠 Simple and beginner-friendly code
- 🖥️ Real-time video display with tracking overlay

---

## 🖼️ Demo

> 📸 **Add your screenshot below this line**  
> *(Tip: After uploading your image to GitHub, add it like this)*  
> `![Tracking Demo](screenshot.png)`

---

## 🧪 Installation

Make sure you have Python installed. Then install the required packages:

```bash
pip install opencv-python numpy

🔧 How to Use
Clone this repository:

bash
Copy
Edit
git clone https://github.com/Teja821/color-object-tracking-opencv.git
cd color-object-tracking-opencv
Run the Python script:

bash
Copy
Edit
python color_tracking.py
Adjust the HSV sliders to match the object color you want to track.

Press ESC to exit the application.

🧠 Sample Code Snippet
python
Copy
Edit
import cv2
import numpy as np

cap = cv2.VideoCapture(0)

while True:
    _, frame = cap.read()
    hsv = cv2.cvtColor(frame, cv2.COLOR_BGR2HSV)

    lower_bound = np.array([35, 100, 100])
    upper_bound = np.array([85, 255, 255])

    mask = cv2.inRange(hsv, lower_bound, upper_bound)
    result = cv2.bitwise_and(frame, frame, mask=mask)

    cv2.imshow('Mask', mask)
    cv2.imshow('Tracking', result)

    if cv2.waitKey(1) == 27:  # ESC key
        break

cap.release()
cv2.destroyAllWindows()
📸 Screenshots
You can add multiple screenshots here
Example:
![Tracking Green Ball](green-ball-demo.png)
![HSV Adjustments](hsv-ui.png)

🤝 Credits
Created by Teja821
Powered by Python 🐍 and OpenCV 📷
