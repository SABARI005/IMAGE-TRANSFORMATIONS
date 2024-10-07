# IMAGE-TRANSFORMATIONS

### Developed By :SABARI S
### Register No:212222240085

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically. 5.Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.
## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('cat.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  # Convert BGR to RGB for Matplotlib

# 1. Translation
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))

# 2. Scaling
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)  # Scale by 1.5x

# 3. Shearing
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shear with factor 0.5
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))

# 4. Reflection (Flip)
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)

# 5. Rotation
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  # Rotate by 45 degrees
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))

# 6. Cropping
cropped_image = image_rgb[50:300, 100:400]  # Crop a portion of the image

# Plot the original and transformed images
plt.figure(figsize=(12, 8))

plt.subplot(2, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')

plt.subplot(2, 3, 2)
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')

plt.subplot(2, 3, 3)
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')

plt.subplot(2, 3, 4)
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')

plt.subplot(2, 3, 5)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')

plt.subplot(2, 3, 6)
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')

plt.tight_layout()
plt.show()

# Plot cropped image separately as its aspect ratio may be different
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()


```
## Output:
### Original image
![{0F2C6E7A-3E73-42B2-8FED-FF041EE2B9A5}](https://github.com/user-attachments/assets/a93a002f-2322-4e57-b65c-9ecbc651dae1)

### i)Image Translation
![{223C33A8-9C9E-4915-A1FD-4049557CB278}](https://github.com/user-attachments/assets/644f6963-5250-4fe7-806d-af91049fdc55)

### ii) Image Scaling
![{4EBADDA9-3940-4549-8545-962A4AADAA31}](https://github.com/user-attachments/assets/d18fd9a6-85b8-4150-8117-f779142baf96)

### iii)Image shearing
![{A290B5EF-FA74-434C-94B9-5E2FA54C45D6}](https://github.com/user-attachments/assets/7a0bd1ea-e57e-4728-bfaf-49cf60c3c8ac)

### iv)Image Reflection
![{C3E59F7C-BEDF-4D84-90EA-9AA652661B1D}](https://github.com/user-attachments/assets/bae21d42-e021-43d3-be26-ff71f03cfe12)

### v)Image Rotation
![{E74F6A67-68BF-4D61-9E5B-24E03BFBA9E0}](https://github.com/user-attachments/assets/5897228e-7645-4142-b4f6-00b679ca3e63)


### vi)Image Cropping
![{4EDA7822-75CA-4699-B3B7-1B9A8B8BC6B7}](https://github.com/user-attachments/assets/00a9a8c9-7f33-4311-bae0-6649263d0a74)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
