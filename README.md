# EXP - 12- Face Detection using Haar Cascades with OpenCV and Matplotlib

### Developed by : Vignesh S
### Register Number : 212223230240

## Aim

To write a Python program using OpenCV to perform the following image manipulations:  
i) Extract ROI from an image.  
ii) Perform face detection using Haar Cascades in static images.  
iii) Perform eye detection in images.  
iv) Perform face detection with label in real-time video from webcam.

## Software Required

- Anaconda - Python 3.7 or above  
- OpenCV library (`opencv-python`)  
- Matplotlib library (`matplotlib`)  
- Jupyter Notebook or any Python IDE (e.g., VS Code, PyCharm)

## Algorithm

### I) Load and Display Images

- Step 1: Import necessary packages: `numpy`, `cv2`, `matplotlib.pyplot`  
- Step 2: Load grayscale images using `cv2.imread()` with flag `0`  
- Step 3: Display images using `plt.imshow()` with `cmap='gray'`

### II) Load Haar Cascade Classifiers

- Step 1: Load face and eye cascade XML files 
### III) Perform Face Detection in Images

- Step 1: Define a function `detect_face()` that copies the input image  
- Step 2: Use `face_cascade.detectMultiScale()` to detect faces  
- Step 3: Draw white rectangles around detected faces with thickness 10  
- Step 4: Return the processed image with rectangles  

### IV) Perform Eye Detection in Images

- Step 1: Define a function `detect_eyes()` that copies the input image  
- Step 2: Use `eye_cascade.detectMultiScale()` to detect eyes  
- Step 3: Draw white rectangles around detected eyes with thickness 10  
- Step 4: Return the processed image with rectangles  

### V) Display Detection Results on Images

- Step 1: Call `detect_face()` or `detect_eyes()` on loaded images  
- Step 2: Use `plt.imshow()` with `cmap='gray'` to display images with detected regions highlighted  

### VI) Perform Face Detection on Real-Time Webcam Video

- Step 1: Capture video from webcam using `cv2.VideoCapture(0)`  
- Step 2: Loop to continuously read frames from webcam  
- Step 3: Apply `detect_face()` function on each frame  
- Step 4: Display the video frame with rectangles around detected faces  
- Step 5: Exit loop and close windows when ESC key (key code 27) is pressed  
- Step 6: Release video capture and destroy all OpenCV windows
### Program :

```
import numpy as np
import cv2 
import matplotlib.pyplot as plt
%matplotlib inline
withglass = cv2.imread('rajini 1.jpeg',0)
group = cv2.imread('rajini 2.jpeg',0)
plt.imshow(withglass,cmap='gray')
plt.show()
plt.imshow(group,cmap='gray')
plt.show()
face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')
def detect_face(img):
    face_img = img.copy()
    face_rects = face_cascade.detectMultiScale(face_img) 
    
    for (x,y,w,h) in face_rects: 
        cv2.rectangle(face_img, (x,y), (x+w,y+h), (255,255,255), 2) 
        
    return face_img

result = detect_face(withglass)
plt.imshow(result,cmap='gray')
plt.show()
result = detect_face(group)
plt.imshow(result,cmap='gray')
plt.show()

def adj_detect_face(img):
    
    face_img = img.copy()
  
    face_rects = face_cascade.detectMultiScale(face_img,scaleFactor=1.2, minNeighbors=5) 
    
    for (x,y,w,h) in face_rects: 
        cv2.rectangle(face_img, (x,y), (x+w,y+h), (255,255,255), 2) 
        
    return face_img
result = adj_detect_face(group)
plt.imshow(result,cmap='gray')
plt.show()

eye_cascade = cv2.CascadeClassifier('haarcascade_eye.xml')
def detect_eyes(img):
    
    face_img = img.copy()
  
    eyes = eye_cascade.detectMultiScale(face_img) 
    
    
    for (x,y,w,h) in eyes: 
        cv2.rectangle(face_img, (x,y), (x+w,y+h), (255,255,255), 2) 
        
    return face_img
result = detect_eyes(model)
plt.imshow(result,cmap='gray')
plt.show()
eyes = eye_cascade.detectMultiScale(withglass)
result = detect_eyes(withglass)
plt.imshow(result,cmap='gray')
plt.show()
```

## DEVELOPED BY : VIGNESH S
## REGISTER NUMBER: 212223230240

### Output :

### INPUT IMAGES :

<img width="735" height="841" alt="rajini 1" src="https://github.com/user-attachments/assets/351fc9a7-cfba-44a2-a96f-05d7d79918e8" />

<img width="416" height="738" alt="rajini 2" src="https://github.com/user-attachments/assets/16a73b7a-a8da-43ff-ad2c-28aa684b1b83" />

<img width="736" height="981" alt="allinone" src="https://github.com/user-attachments/assets/969066ad-dfd5-45aa-9e0a-3ffbefdc2e79" />


### FACE DETECTION :
<img width="367" height="657" alt="image" src="https://github.com/user-attachments/assets/bde34dd1-1665-4e97-a042-26bbc90b4316" />

<img width="558" height="657" alt="image" src="https://github.com/user-attachments/assets/10f8365a-e321-4ddd-b67b-e2f733ec3ceb" />


### EYE DETECTION :

<img width="367" height="657" alt="image" src="https://github.com/user-attachments/assets/7d5fbc14-d42a-4822-b07b-738f2db77e5c" />

### Result :
Thus, to write a Python program using OpenCV to perform image manipulations for the given objectives is executed sucessfully.
