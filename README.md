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
## Name: Sairam V
### Register No: 212225230237


```
# Import required libraries

import cv2
import numpy as np
import matplotlib.pyplot as plt
from PIL import Image
img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

img.shape
# Display the grayscale image.

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()

# Plot the histogram of the grayscale image
# Display the images
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
# Perform histogram equalization
# Equalize histogram
img_eq = cv2.equalizeHist(img)

# Display the images.
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
# Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.

# Display the images.
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)

 #Convert to HSV.
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
# Perform histogram equalization
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
# Convert back to BGR format
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
# Display
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()

# Plot the histogram of colour image
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()



```

---

##  Output

### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast
<img width="714" height="450" alt="image" src="https://github.com/user-attachments/assets/f00ef505-8756-43fb-8d11-097f0af164ad" />
 <img width="715" height="510" alt="image" src="https://github.com/user-attachments/assets/29e70a7b-dac4-4d8b-8896-b8aee726e19a" />
 <img width="708" height="538" alt="image" src="https://github.com/user-attachments/assets/0a57b35a-b4f7-4373-b9a8-fecce2bf5d8a" />

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  
<img width="692" height="428" alt="image" src="https://github.com/user-attachments/assets/d7d09827-5de9-40ad-b99e-442549f88dae" />
<img width="713" height="526" alt="image" src="https://github.com/user-attachments/assets/a7812089-f4fe-42b0-9cd7-8ac10bd26b60" />

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
