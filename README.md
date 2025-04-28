# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm
### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
## Step5:
Use Otsu's method to segment the image and display the results.

## Program
```
Developed By: Samakash R S
Reg.NO: 212223230182
```

```python
# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Read the Image and convert to grayscale
image = cv2.imread('GATE.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('GATE.jpg',0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

#Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
# Display the results

for i in range(0,9):
    plt.figure(figsize=(10,10))
  
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()

```
## Output


### Gray Image
![alt text](<Screenshot 2025-04-28 183359.png>)

### Global Thresholding
![alt text](<Screenshot 2025-04-28 183412.png>)
![alt text](<Screenshot 2025-04-28 183425.png>)
![alt text](<Screenshot 2025-04-28 183433.png>)
![alt text](<Screenshot 2025-04-28 183440.png>)

### Adaptive Thresholding
![alt text](<Screenshot 2025-04-28 183502.png>)
![alt text](<Screenshot 2025-04-28 183510.png>)

### Optimum Global Thesholding using Otsu's Method
![alt text](<Screenshot 2025-04-28 183454.png>)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
