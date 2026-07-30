# Record-Histogram-Processing.

### DEVELOPED BY : Jeevan Vishal.G.D
### REG NO : 212224240062

## AIM : 
To perform histogram processing and histogram equalization on grayscale and color images using OpenCV.
To enhance image contrast and compare the original and equalized histograms.

## SOFTWARE REQUIRED :
```
--> Anaconda - Python 3.7
--> Jupyter Notebook (for interactive development and execution)
```

## ALGORITHM :
### Step 1:
Read the input image in grayscale and display the original image with its histogram.

### Step 2:
Apply histogram equalization to the grayscale image using cv2.equalizeHist().

### Step 3:
Display the equalized grayscale image and its histogram for comparison.

### Step 4:
Read the original image in color and convert it from BGR to HSV color space.

### Step 5:
Apply histogram equalization to the V (Value) channel of the HSV image.

### Step 6:
Convert the modified HSV image back to BGR color space and display the enhanced color image.

### Step 7:
Compare the original and equalized images along with their histograms to observe the improvement in contrast.

## PROGRAM :

### Read and Display the Original Grayscale Image :
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('Bird.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')
plt.show()

```

### Perform Histogram Equalization on Grayscale Image
```py
img_eq = cv2.equalizeHist(img)

plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

```

### Perform Histogram Equalization on Color Image
```py
img = cv2.imread('Bird.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Color Image')
plt.show()

plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Histogram Equalized')
plt.show()

```
###  Compare Original and Equalized Images with Histograms
```py
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')
plt.show()

```

1. 

<img width="632" height="368" alt="image" src="https://github.com/user-attachments/assets/05bb2887-13d9-4e03-9aef-26f5a38728ad" />


2.


<img width="668" height="490" alt="image" src="https://github.com/user-attachments/assets/19c6a2c0-710a-4e3a-bb94-d0364da28819" />


3.
Text(0.5,1.0,'Equalized Histogram')
<img width="660" height="495" alt="image" src="https://github.com/user-attachments/assets/2946bd08-abdc-4a9a-8c90-ddcf2825611a" />


3.
<img width="628" height="352" alt="image" src="https://github.com/user-attachments/assets/a153ef38-6d5a-432a-9f37-153e8230acaf" />

4.
<img width="642" height="357" alt="image" src="https://github.com/user-attachments/assets/9f53de0c-047a-4214-a283-5d085cdb1f5e" />

5.
<img width="665" height="485" alt="image" src="https://github.com/user-attachments/assets/5563a08a-15ee-4fa8-a0b0-faaeec59bdfe" />

6.
<img width="691" height="462" alt="image" src="https://github.com/user-attachments/assets/66ba63ae-7562-499d-8cb3-074d500a281a" />

7.
<img width="825" height="282" alt="image" src="https://github.com/user-attachments/assets/762117a7-fb74-4f23-9dc5-27b3f1a6663d" />


 ## RESULT :

Histogram equalization successfully improved the image contrast by redistributing pixel intensity values.
The equalized images showed enhanced visual quality with a more uniform intensity distribution compared to the original images.
