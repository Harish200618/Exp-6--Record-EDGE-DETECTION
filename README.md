# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

- **Name:** Harish S
- **Register No:** 212224240052

---
## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Chennai_Central.jpg')  
plt.imshow(image[:,:,::-1])
plt.title('Original Image')
plt.axis('off')
sobelx  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 1, dy = 0, ksize = 3) 
sobely  = cv2.Sobel(src = gray_image, ddepth = cv2.CV_64F, dx = 0, dy = 1, ksize = 3)

sobelx = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)  
sobely = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)  
sobel_combined = cv2.magnitude(sobelx, sobely) 
plt.figure(figsize = (12,16))

plt.subplot(321)
plt.axis('off')
plt.imshow(image[:,:,::-1])
plt.title('Original')

plt.subplot(322)
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale')

plt.subplot(323)
plt.axis('off')
plt.imshow(sobelx)
plt.title('Sobel-X Edge Map')

plt.subplot(324)
plt.axis('off')
plt.imshow(sobely)
plt.title('Sobel-Y Edge Map')
Text(0.5, 1.0, 'Sobel-Y Edge Map')
plt.figure(figsize = (7,7))

plt.axis('off')
plt.imshow(sobel_combined, cmap='gray')
plt.title('sobel_combined')

plt.show()
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.figure(figsize = (12,16))

plt.subplot(121)
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title('Inputimage (Gray Image)')

plt.subplot(122)
plt.imshow(laplacian, cmap='gray')
plt.axis('off')
plt.title('Output Image (laplacian)')

plt.show()
```
## Output

###  Sobel Edge Detector
- Detects edges in horizontal and vertical directions  
- Produces gradient-based edge map
- <img width="562" height="415" alt="download" src="https://github.com/user-attachments/assets/62a59996-39da-4ad9-b826-df4b5b26dd8a" />


###  Prewitt Edge Detector
- Similar to Sobel but simpler kernel  
- Detects directional edges
- <img width="562" height="415" alt="download" src="https://github.com/user-attachments/assets/dbb14ebe-cd8c-4e4c-9e59-8f899d3431dc" />


###  Roberts Edge Detector
- Detects edges using diagonal gradients  
- Sensitive to noise
- <img width="562" height="415" alt="download" src="https://github.com/user-attachments/assets/e8232158-4835-4b6a-9880-97bcc509c528" />


###  Laplacian Edge Detector
- Detects edges using second-order derivatives  
- Highlights rapid intensity changes  
<img width="950" height="333" alt="download" src="https://github.com/user-attachments/assets/6e8743ea-ed0a-45bd-94af-90eeca6d0f87" />

###  Canny Edge Detector
- Multi-stage edge detection  
- Produces clean and thin edges
- <img width="794" height="284" alt="download" src="https://github.com/user-attachments/assets/76a04287-6454-4957-b7cd-9839ea402a7e" />


---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
