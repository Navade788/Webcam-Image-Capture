# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program

### Developed By:
**Name:** S.NAVADEEP 

### Register No: 212224230180

# Import required libraries
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)

# Read a single frame
ret, frame = cap.read()

if ret:
    # Write the frame as a JPG file
    cv2.imwrite("captured_image.jpg", frame)
    print("Image saved as captured_image.jpg")
else:
    print("Failed to capture image")
# Display the captured frame using Matplotlib
if ret:
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    
    plt.imshow(frame_rgb)
    plt.title("Captured Image")
    plt.axis('off')
    plt.show()
# To Display the video
for i in range(30):
    ret, frame = cap.read()

    if not ret:
        break

    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.title("Live Video")
    plt.axis('off')
    plt.show()

# Display the video by resizing the window

for i in range(30):   # runs only 30 frames
    ret, frame = cap.read()

    if not ret:
        break

    resized = cv2.resize(frame, (640, 480))
    resized_rgb = cv2.cvtColor(resized, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(resized_rgb)
    plt.title("Resized Video (640x480)")
    plt.axis('off')
    plt.show()
# Rotate and display the video

for i in range(30):   # runs only 30 frames
    ret, frame = cap.read()

    if not ret:
        break

    rotated = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    rotated_rgb = cv2.cvtColor(rotated, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(rotated_rgb)
    plt.title("Rotated Video (90°)")
    plt.axis('off')
    plt.show()

---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`

### ii) Display the video
Live webcam video is displayed

### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
