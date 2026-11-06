# EXPERIMENT 5 – IMPLEMENTATION OF FILTERS
# Name: Raha Priya Dharshini M
# Reg no.: 212224240124

## Aim
To implement different image filtering techniques using OpenCV and Python to perform image smoothing and edge enhancement.

## Software Requirements
- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Jupyter Notebook

## Procedure

1. Import the required libraries.
2. Read the input image using OpenCV.
3. Convert the image from BGR to RGB colour space.
4. Apply the Average Filter using a kernel of size 11 × 11.
5. Apply the Weighted Average Filter using a 3 × 3 kernel.
6. Apply Gaussian Blur using `cv2.GaussianBlur()`.
7. Apply Median Blur using `cv2.medianBlur()`.
8. Apply the Laplacian Kernel using `cv2.filter2D()`.
9. Apply the Laplacian Operator using `cv2.Laplacian()`.
10. Display and compare the original image with the filtered outputs.

## Code:
```

import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("Ganesh_D.jpeg")

if image1 is None:
    raise FileNotFoundError("Ganesh_D.jpeg not found")

image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

# Average Filter
kernel = np.ones((11, 11), np.float32) / 169
image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9, 9))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()

# Weighted Average Filter
kernel1 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

image3 = cv2.filter2D(image2, -1, kernel1)

plt.figure(figsize=(9, 9))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

# Gaussian Blur
gaussian_blur = cv2.GaussianBlur(image2, (33, 33), 0, 0)

plt.figure(figsize=(9, 9))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

# Median Blur
median = cv2.medianBlur(image2, 13)

plt.figure(figsize=(9, 9))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()

# Laplacian Kernel
kernel2 = np.array([[-1, -1, -1],
                    [2, -2, 1],
                    [2, 1, -1]])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.figure(figsize=(9, 9))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

# Laplacian Operator
laplacian = cv2.Laplacian(image2, cv2.CV_64F)

plt.figure(figsize=(9, 9))
plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output Screenshots

### 1. Average Filter
<img width="1362" height="570" alt="image" src="https://github.com/user-attachments/assets/bdb2b9d5-6d36-41a4-ad2d-6383ea4c8d10" />


### 2. Weighted Average Filter
<img width="1348" height="426" alt="image" src="https://github.com/user-attachments/assets/cbc4894f-f5f8-4805-ba09-35e599efbb31" />


### 3. Gaussian Blur
<img width="1357" height="420" alt="image" src="https://github.com/user-attachments/assets/bc8cf911-5881-410a-8a8e-63b0ed957bdf" />


### 4. Median Blur
<img width="1371" height="560" alt="image" src="https://github.com/user-attachments/assets/562ed245-999d-42a4-8110-ea944532c5f0" />


### 5. Laplacian Kernel
<img width="1348" height="420" alt="image" src="https://github.com/user-attachments/assets/9bc92552-8568-4a32-a884-4afbf5051c61" />


### 6. Laplacian Operator
<img width="1356" height="431" alt="image" src="https://github.com/user-attachments/assets/9bd0582b-fc0a-4f63-bfae-c13d733404a2" />


## Result
Thus, different image filtering techniques including Average Filter, Weighted Average Filter, Gaussian Blur, Median Blur, Laplacian Kernel and Laplacian Operator were successfully implemented using OpenCV and Python. The filtered images were displayed and compared with the original image.
