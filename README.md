# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** Nivetha N
### Register No: 212225040290
## Program
---python

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```python
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.show()
```
```python
img_eq = cv2.equalizeHist(img)
```
```python
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()
```
```python
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()
```
```python
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```
```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
```python
plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.show()
```
```python
plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed
- <img width="810" height="502" alt="Screenshot 2026-07-31 103544" src="https://github.com/user-attachments/assets/932614b8-556e-41f0-b15a-344a6d670bf5" />

- Histogram of original grayscale image is plotted
- <img width="783" height="546" alt="Screenshot 2026-07-31 103711" src="https://github.com/user-attachments/assets/d44d356f-9fe6-4248-b862-961d758c8be0" />

- Enhanced image after histogram equalization is displayed
- <img width="812" height="557" alt="Screenshot 2026-07-31 103742" src="https://github.com/user-attachments/assets/9ce2a317-bd30-4701-837a-3656121014f5" />

- Histogram of enhanced grayscale image shows improved contrast
- <img width="758" height="498" alt="Screenshot 2026-07-31 103838" src="https://github.com/user-attachments/assets/5c80402f-382e-4734-aa6a-7632c8da4ef2" />


### Color Image Histogram Equalization

- Original color image is displayed
- <img width="758" height="498" alt="Screenshot 2026-07-31 103838" src="https://github.com/user-attachments/assets/8020c2d1-e02a-4540-ada5-dc581ac9f80e" />

- Histogram of B, G, R channels is plotted
- <img width="497" height="411" alt="Screenshot 2026-07-31 104047" src="https://github.com/user-attachments/assets/871fff48-7c1a-4993-b915-76ee8729f995" />

- Enhanced image after HSV-based equalization is displayed
- <img width="965" height="336" alt="Screenshot 2026-07-31 104122" src="https://github.com/user-attachments/assets/483e24a4-87fb-4705-8b5c-2cc3cbd7a634" />

- Histogram of enhanced image shows better intensity distribution
- <img width="985" height="427" alt="Screenshot 2026-07-31 104139" src="https://github.com/user-attachments/assets/2e7cd69e-0b12-4797-960b-256efa898386" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
