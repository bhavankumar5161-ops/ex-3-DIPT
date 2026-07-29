# Histogram Equalization Using OpenCV (Grayscale & Color Images)
## Developed by: P.Bhavankumar
### Register no: 212225240026
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
**Name:** __P.Bhavankumar________________  

### Register No:
___212225240026_________________________  

---
# program

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.ashow()

plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()

plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')


##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed:

<img width="740" height="535" alt="Screenshot 2026-07-29 082448" src="https://github.com/user-attachments/assets/1c10a2de-4941-40cb-8955-4d3efd8c7023" />
 
- Histogram of original grayscale image is plotted :

<img width="778" height="591" alt="Screenshot 2026-07-29 082555" src="https://github.com/user-attachments/assets/733443f6-0ee6-457e-ad30-7ba0880370a9" />

- Enhanced image after histogram equalization is displayed:

<img width="782" height="590" alt="Screenshot 2026-07-29 082632" src="https://github.com/user-attachments/assets/4cbcde6e-f4c0-4797-b1a8-fc9263885506" />
  
- Histogram of enhanced grayscale image shows improved contrast :

<img width="742" height="537" alt="Screenshot 2026-07-29 082718" src="https://github.com/user-attachments/assets/3a78d7c5-80e8-44f8-9be3-9fdda953254d" />


### Color Image Histogram Equalization

- Original color image is displayed:

- <img width="740" height="536" alt="Screenshot 2026-07-29 082846" src="https://github.com/user-attachments/assets/1d189568-e444-4937-83d6-27ca6a36380e" />

- Histogram of B, G, R channels is plotted :

- <img width="795" height="592" alt="Screenshot 2026-07-29 082923" src="https://github.com/user-attachments/assets/524e0b73-9370-4db7-9915-6ac07c10b31e" />

- Enhanced image after HSV-based equalization is displayed:

- <img width="1097" height="312" alt="Screenshot 2026-07-29 083030" src="https://github.com/user-attachments/assets/a941a6d2-a67f-4af8-aa5c-32e9941e52fb" />

- Histogram of enhanced image shows better intensity distribution:

- <img width="1103" height="323" alt="Screenshot 2026-07-29 083101" src="https://github.com/user-attachments/assets/675ebf97-3320-49ef-8a0e-997da3da6c2e" />


---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
