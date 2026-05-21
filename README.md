# Detect-The-Lines-Using-Hough-Transform  Lane Detection
## NAME :  DINESH R
## REG NO: 212224240037
##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

**Important Instruction:**
👉 Write code **ONLY in places marked as `# Your Code Here`**
👉 Do NOT modify any other part of the code

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---
## Algorithm
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.


## Read image and convert it to grayscale image
### Importing required packages
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
```
### Read The Image
```
img=cv2.imread("me.jpeg",0)
img_c=cv2.imread("me.jpeg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
```
### Convert to Scale
```
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
```
### Display original Image
```
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
```
### Display the Gray Image
```
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Find the edges in the image using canny detector and display
```PY
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```PY
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```PY
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```PY
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```

## Output

### Input image 

<img width="872" height="493" alt="image" src="https://github.com/user-attachments/assets/40c51131-f8bc-4b6f-959b-701fb2cfcbc9" />

### grayscale image


<img width="486" height="277" alt="image" src="https://github.com/user-attachments/assets/e6673478-ca49-43b2-af93-8239e21028e2" />

<br>

### Canny Edge detector output

<img width="786" height="486" alt="image" src="https://github.com/user-attachments/assets/fef380e7-c8c0-45e2-bb38-750d04bfe0e0" />

<br>

### Display the result of Hough transform

<img width="757" height="464" alt="image" src="https://github.com/user-attachments/assets/617e05f0-933d-4a42-83d4-ed6199444c81" />

<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
