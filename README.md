# Real-Time Object Measurement using OpenCV📷

This project uses Computer Vision to measure the dimensions (Width and Height) of objects in real-time. It uses an **A4 size paper** as a reference object to calibrate the pixel-to-centimeter ratio, allowing for accurate measurements of any object placed on it.

## 🚀 How It Works

1. **Reference Detection:** The system detects an A4 paper (210mm x 297mm) using contours.
2. **Perspective Warp:** It "flattens" the view of the paper to remove camera angle distortion (Bird's Eye View).
3. **Object Detection:** It identifies objects placed on the paper.
4. **Measurement:** Using the known dimensions of the A4 paper, it calculates the width and height of the objects in centimeters.

---

## 🖼️ Output
 <img width="1920" height="1080" alt="Screenshot (73)" src="https://github.com/user-attachments/assets/e87facba-7321-42d9-af14-b99097206269" />

 <img width="1920" height="1080" alt="Screenshot (76)" src="https://github.com/user-attachments/assets/9cad98da-cc78-4811-86eb-2fb42bc505df" />

 <img width="1920" height="1080" alt="Screenshot (70)" src="https://github.com/user-attachments/assets/505ffa11-152c-426d-aa23-71510643f5cd" />


---

## 🛠 Prerequisites

Before running the project, ensure you have the following installed:

* Python 3.12
* OpenCV (`cv2`)
* NumPy

Install dependencies via pip:

```bash
pip install opencv-python numpy

```

---

## 📂 Project Structure

* `ObjectMeasurement.py`: The primary script that handles the webcam feed and logic.
* `utlis.py`: Helper functions for contour detection, image warping, and distance calculation.
* `1.jpg`: Default image path if the webcam is not being used.

---

## ⚙️ Setup & Usage

1. **Placement:** Place a white **A4 size paper** on a dark, flat surface.
2. **Camera:** Mount your camera/webcam directly above the paper (Top-down view) for the best results.
3. **Run the script:**
```bash
python ObjectMeasurement.py

```


4. **Interaction:** * The "Original" window shows the raw feed.
* The "A4" window shows the processed measurement of objects found on the paper.



---

## 📊 Key Functions (utlis.py)

* `getContours`: Filters the image using Canny edge detection and finds shapes based on area.
* `reorder`: Ensures the four corner points of the paper are always in the same order (Top-Left, Top-Right, Bottom-Left, Bottom-Right).
* `warpImg`: Crops and transforms the paper area to a standard rectangular view.
* `findDis`: Uses the Euclidean distance formula to calculate the length between two points:



---

## ⚠️ Notes for Better Accuracy

* **Lighting:** Ensure even lighting to avoid shadows that the software might mistake for object edges.
* **Contrast:** Use a background color that contrasts well with the A4 paper (e.g., a dark table).
* **Calibration:** If your measurements are slightly off, adjust the `scale` variable in `ObjectMeasurement.py`.



## 🤝 Contributing

Feel free to fork this project, report issues, or submit pull requests to improve the detection algorithm!

---

