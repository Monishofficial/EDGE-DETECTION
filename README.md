# Exp-6 EDGE-DETECTION

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

## Program:

```
# Developed By: MONISH N
# Register Number: 212223240097


import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load image with safe path
image = cv2.imread(r'C:\Users\admin\Downloads\eif.jpeg')  
if image is None:
    print("Error: Could not load the image. Check the file path.")
else:
    # Convert to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Sobel edge detection
    sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=3)
    sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=3)
    sobel_edge = cv2.magnitude(sobel_x, sobel_y)
    sobel_edge = cv2.convertScaleAbs(sobel_edge)

    # Laplacian edge detection
    laplacian_edge = cv2.Laplacian(gray_image, cv2.CV_64F)
    laplacian_edge = cv2.convertScaleAbs(laplacian_edge)

    # Canny edge detection
    canny_edge = cv2.Canny(gray_image, 100, 200)

    # Display results
    plt.figure(figsize=(10, 8))
    plt.subplot(2, 2, 1)
    plt.imshow(gray_image, cmap='gray')
    plt.title("Grayscale Image")
    plt.axis('off')

    plt.subplot(2, 2, 2)
    plt.imshow(laplacian_edge, cmap='gray')
    plt.title("Laplacian Edge Detector")
    plt.axis('off')

    plt.subplot(2, 2, 3)
    plt.imshow(canny_edge, cmap='gray')
    plt.title("Canny Edge Detector")
    plt.axis('off')

    plt.subplot(2, 2, 4)
    plt.imshow(sobel_edge, cmap='gray')
    plt.title("Sobel Edge Detector")
    plt.axis('off')

    plt.tight_layout()
    plt.show()

```
## Output:

![download](https://github.com/user-attachments/assets/9dab6dbb-41eb-4e95-81ee-af4443a77f49)



## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
