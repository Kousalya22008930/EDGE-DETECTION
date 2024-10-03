# EDGE-DETECTION
## Aim:
To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale

### Step4:
Using Sobel operator from cv2,detect the edges of the image.

### Step5:

Using Laplacian operator from cv2,detect the edges of the image and Using Canny operator from cv2,detect the edges of the image.

## Program and Output:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('cat.jpg') # Replace with your image path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Original Image
plt.figure(figsize=(7,3))
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/45bdbfc7-bb21-4cb9-96e3-0046687c4090)

### SOBEL EDGE DETECTOR
```python
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  # Sobel in x direction
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  # Sobel in y direction
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  # Combine both directions
plt.figure(figsize=(7,3))
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/9f7c489c-c0ec-4dfa-86c9-c873b4c0680e)

### LAPLACIAN EDGE DETECTOR
```python
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.figure(figsize=(7,3))
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/97d86b58-8268-4b3d-a16a-92a15086a696)

### CANNY EDGE DETECTOR
```python
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.figure(figsize=(7,3))
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
![image](https://github.com/user-attachments/assets/b045f22f-078b-4164-b56e-c617b60daeb7)

## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
