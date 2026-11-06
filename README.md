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

## PROGRAM

Developed By: Pragatheeshraaj D

Register Number: 212224230199

### Import Python Necessary Libraries

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Read and Display the Original Grayscale Image

```
img = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')plt.show()
```

### Plot the Histogram of the Original Grayscale Image

```
plt.hist(img.ravel(), 256, range=[0, 256])
plt.title('Original Image')plt.show()
```

### Apply Histogram Equalization on the Grayscale Image

```
img_eq = cv2.equalizeHist(img)
```

### Plot the Histogram of the Equalized Grayscale Image

```
plt.hist(img_eq.ravel(), 256, range=[0, 256])
plt.title('Equalized Histogram')plt.show()
```

### Display the Enhanced Grayscale Image

```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```

### Read the Original Color Image

```
img = cv2.imread('WhatsApp Image 2026-10-17 at 10.57.14 AM.jpeg', cv2.IMREAD_COLOR)
```

### Convert the Color Image from BGR to HSV

```
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
```

### Apply Histogram Equalization on the V Channel

```
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```

### Convert the Enhanced HSV Image Back to BGR

```
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```

### Display the Enhanced Color Image

```
plt.imshow(img_eq[:, :, ::-1])plt.title('Equalized Image')plt.show()
```

### Plot the Histogram of the Equalized Color Image

```
plt.hist(img_eq.ravel(), 256, range=[0, 256])plt.title('Histogram Equalized')plt.show()
```

### Display Original and Equalized Color Images

```
plt.figure(figsize=(20, 10))
plt.subplot(221)plt.imshow(img[:, :, ::-1])plt.title('Original Color Image')
plt.subplot(222)plt.imshow(img_eq[:, :, ::-1])plt.title('Equalized Image')
plt.show()
```

### Compare Original and Equalized Color Image Histograms

```
plt.figure(figsize=[15, 4])
plt.subplot(121)plt.hist(img.ravel(), 256, range=[0, 256])plt.title('OriginalImage')
plt.subplot(122)plt.hist(img_eq.ravel(), 256, range=[0, 256])plt.title('Histogram Equalized')
plt.show()
```


##  Output

### Original grayscale image.
<img width="417" height="420" alt="image" src="https://github.com/user-attachments/assets/a28b485d-523a-4ab7-b2fd-1992db8d7052" />



### Histogram of the original grayscale image.

<img width="853" height="428" alt="image" src="https://github.com/user-attachments/assets/a87536bc-3d9b-4b5e-87a5-27c0218cecda" />


### Equalized grayscale histogram.

<img width="747" height="457" alt="image" src="https://github.com/user-attachments/assets/5b09daab-6e81-4407-b2a1-5a7a4b636c0f" />


### Enhanced grayscale image.
<img width="510" height="418" alt="image" src="https://github.com/user-attachments/assets/bdccc752-cb01-4bc7-8fac-adbe711d80b7" />



### Original color image.
<img width="411" height="435" alt="image" src="https://github.com/user-attachments/assets/af9b1756-4855-477e-9fd0-87fe9a2a04e9" />

<img width="655" height="415" alt="image" src="https://github.com/user-attachments/assets/3784169b-d41d-4129-bd4b-c0af0847c053" />



### Enhanced color image using HSV equalization.
<img width="1122" height="390" alt="image" src="https://github.com/user-attachments/assets/ec051a7e-4faf-4f81-ac30-571cd7a5736f" />



### Histogram comparison of original and equalized color images.
<img width="1088" height="362" alt="image" src="https://github.com/user-attachments/assets/fe351ce3-cff6-4157-9ba3-d911a2a68de6" />


## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
