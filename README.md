# Exp-8-Record-THRESHOLDING

# THRESHOLDING-OPENCV

## Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

---

## Software Required

1. Anaconda – Python 3.7
2. Jupyter Notebook / VS Code
3. OpenCV (`cv2`)
4. NumPy
5. Matplotlib

---

## Developed By

- **Name:** RITHIKA K
- **Register No:** 212225040343

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary Python packages, including NumPy, Matplotlib, and OpenCV.

### Step 2:
Read the input image using `cv2.imread()` and convert the image into grayscale.

### Step 3:
Apply Global Thresholding using `cv2.threshold()` to segment the image into different regions.

### Step 4:
Apply Adaptive Thresholding using `cv2.adaptiveThreshold()` with Mean and Gaussian methods.

### Step 5:
Apply Otsu's Thresholding using `cv2.threshold()` with the `cv2.THRESH_OTSU` flag to automatically determine the optimum threshold value.

### Step 6:
Display the original grayscale image and all the thresholded images using Matplotlib.

---

## Program

```python
# Developed By: RITHIKA K
# Register No: 212225040343

# Load the necessary packages
import numpy as np
import matplotlib.pyplot as plt
import cv2

# Step 2: Read the image and convert to grayscale
image = cv2.imread('Rithi.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')

# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```

---

## Output

### Original Image

<img width="297" height="237" alt="Screenshot 2026-11-22 210509" src="https://github.com/user-attachments/assets/5bb436f5-e11c-410c-b969-48e531b49c1d" />


###  Global Thresholding , Adaptive Thresholding and Otsu's Method

<img width="562" height="475" alt="image" src="https://github.com/user-attachments/assets/f45ba343-b94d-49ee-b0a4-368e3ed830ae" />


---

## Result

Thus, the input image was successfully segmented using Global Thresholding, Adaptive Thresholding, and Optimum Global Thresholding using Otsu's method in Python and OpenCV.
