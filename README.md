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

### Step5:
Use Otsu's method to segment the image and display the results.

## PROGRAM
### Developed By : K MADHAVA REDDY
### Register Number : 212223240064


### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```python
image = cv2.imread('pandaa.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('pandaa.jpg',0)
```
### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## OUTPUT

### Original Image
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/249f3bab-430a-43e9-a715-5138937c23bf)


### Global Thresholding
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/d5f8a99c-3605-4c74-90ba-2ecddf17225d)
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/289614ec-7c47-4644-8eba-6f0ab521851c)
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/a773ec00-da3c-4767-92e7-35f50e4c9216)
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/4a4eb7b1-8272-4e14-a320-d4811c04ab4a)
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/2875934e-acde-475d-a22b-bc996baa95d4)



### Adaptive Thresholding
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/a0d13dc5-fa2d-42d7-ac6a-67299fc4c993)
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/7f83ee09-8c27-4419-9207-b800c8a0b48d)




### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Madhavareddy09/THRESHOLDING-/assets/145742470/2200a789-f667-44f6-8a61-5059e9ffd7bb)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
