# Implementation-of-filter
# Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

# Software Required:
Anaconda - Python 3.7

# Algorithm:
## Step1
Import the required libraries.
## Step2
Convert the image from BGR to RGB.
## Step3
Apply the required filters for the image separately.
## Step4
Plot the original and filtered image.
## Step5
End the program.
# Program:
```
Developed By   : YUVARAJ V
Register Number: 212223230252
```
## 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image=cv2.imread("wolf.jpg")
image1=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((5,5),dtype = np.float32)/25
image2 = cv2.filter2D(image1, ddepth = -1, kernel = kernel)

plt.figure(figsize=(20, 8))
plt.subplot(1,2,1); plt.imshow(image1); plt.title("Original Image"); plt.axis("off")
plt.subplot(1,2,2); plt.imshow(image2); plt.title("Convolution Result"); plt.axis("off")

```
ii) Using Weighted Averaging Filter
```Python
avg_fltr = cv2.blur(image1, (15,15))

plt.figure(figsize=(18, 9))
plt.subplot(1,2,1); plt.imshow(image1); plt.title("Original Image"); plt.axis("off")
plt.subplot(1,2,2); plt.imshow(avg_fltr); plt.title("Average Filter Result"); plt.axis("off")
```
iii) Using Gaussian Filter
```Python
gaussian_filter = cv2.GaussianBlur(image1, (23,23), 0, 0)

plt.figure(figsize=(18, 9))
plt.subplot(1,2,1); plt.imshow(image1); plt.title("Original Image"); plt.axis("off")
plt.subplot(1,2,2); plt.imshow(gaussian_filter); plt.title("Gaussian Filter Result"); plt.axis("off")
```
iv)Using Median Filter
```Python
median_filter = cv2.medianBlur(image1, 13)

plt.figure(figsize=(18, 9))
plt.subplot(1,2,1); plt.imshow(image1); plt.title("Original Image"); plt.axis("off")
plt.subplot(1,2,2); plt.imshow(median_filter); plt.title("Median Filter Result"); plt.axis("off")

```

## 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
laplacian_kernel = np.array([[0, -1, 0],
                             [-1, 5, -1],
                             [0, -1, 0]])
sharpened_laplacian_kernel = cv2.filter2D(image1, -1, kernel = laplacian_kernel)

plt.figure(figsize=(18, 9))
plt.subplot(1,2,1); plt.imshow(image1); plt.title("Original Image"); plt.axis("off")
plt.subplot(1,2,2); plt.imshow(sharpened_laplacian_kernel); plt.title("Laplacian Filter Result"); plt.axis("off")
```
ii) Using Laplacian Operator
```Python
gray_image = cv2.cvtColor(image1, cv2.COLOR_RGB2GRAY)
laplacian_operator = cv2.Laplacian(gray_image, cv2.CV_64F)
laplacian_operator = np.uint8(np.absolute(laplacian_operator))

plt.figure(figsize=(18, 9))
plt.subplot(1,3,1); plt.imshow(image1); plt.title("Original Image"); plt.axis("off")
plt.subplot(1,3,2); plt.imshow(gray_image, cmap = 'gray'); plt.title("Gray Image"); plt.axis("off")
plt.subplot(1,3,3); plt.imshow(laplacian_operator, cmap = 'gray'); plt.title("Laplacian Filter Result"); plt.axis("off")

```

# OUTPUT:
## 1. Smoothing Filters
i) Using Averaging Filter
<img width="1246" height="457" alt="image" src="https://github.com/user-attachments/assets/58858972-7bf5-482c-9076-ede9960f5690" />


ii)Using Weighted Averaging Filter
<img width="1268" height="436" alt="image" src="https://github.com/user-attachments/assets/a82813ac-9fc8-4c66-86e6-ee409a8bebde" />


iii)Using Gaussian Filter
<img width="1245" height="426" alt="image" src="https://github.com/user-attachments/assets/da0d1fae-9399-44be-9cde-0b8d0e19a24d" />


iv) Using Median Filter
<img width="1238" height="314" alt="image" src="https://github.com/user-attachments/assets/1a26c7c5-f3d7-417d-ac15-c894d17ed571" />


## 2. Sharpening Filters
i) Using Laplacian Kernal
<img width="1246" height="428" alt="image" src="https://github.com/user-attachments/assets/08f3c882-96de-4201-8ade-ed5d2f399608" />


ii) Using Laplacian Operator
<img width="1252" height="295" alt="image" src="https://github.com/user-attachments/assets/8800dee4-fb47-4431-ba65-b6a6a15d4869" />

# Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
