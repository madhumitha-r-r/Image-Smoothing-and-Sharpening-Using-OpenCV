# Experiment: Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Algorithm

1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Read the input image (`spider.png`).
3. Convert the image from BGR to RGB format for display.
4. Apply Averaging Filter using `cv2.filter2D()`.
5. Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.
6. Apply Gaussian Filter using `cv2.GaussianBlur()`.
7. Apply Median Filter using `cv2.medianBlur()`.
8. Apply Laplacian Sharpening using a kernel with `cv2.filter2D()`.
9. Convert the image to grayscale and apply the Laplacian Operator using `cv2.Laplacian()`.
10. Display all filtered images for comparison.

## Python Program
## Developed by 
### NAME: MADHUMITHA R R
### REG NO :212224240083

### 1. Smoothing Filters

**i) Using Averaging Filter**

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("spider.png")
image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)

kernel = np.ones((11, 11), np.float32) / 121
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
```

**ii) Using Weighted Averaging Filter**

```python
kernel1 = np.array([[1, 2, 1],
                    [2, 4, 2],
                    [1, 2, 1]]) / 16

image3 = cv2.filter2D(image2, -1, kernel1)

plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

**iii) Using Gaussian Filter**

```python
gaussian_blur = cv2.GaussianBlur(image2, (33, 33), 0, 0)

plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

**iv) Using Median Filter**

```python
median = cv2.medianBlur(image2, 13)

plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters

**i) Using Laplacian Linear Kernel**

```python
kernel2 = np.array([[-1, -1, -1],
                    [2, -2, 1],
                    [2, 1, -1]])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

**ii) Using Laplacian Operator**

```python
gray = cv2.cvtColor(image2, cv2.COLOR_RGB2GRAY)

laplacian = cv2.Laplacian(gray, cv2.CV_64F)

plt.imshow(laplacian, cmap="gray")
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## Output

The following outputs are obtained:

- Original Image

  <img width="267" height="370" alt="image" src="https://github.com/user-attachments/assets/06138089-a6d4-4c63-a346-d925c8daa945" />

- Average Filter Image

  <img width="297" height="380" alt="image" src="https://github.com/user-attachments/assets/df9d81bb-7b1d-40bf-839e-35f1856bee69" />


- Weighted Average Filter Image

<img width="223" height="270" alt="image" src="https://github.com/user-attachments/assets/da1203a6-5ae5-44ee-8a51-476dbd23f7ab" />

  
- Gaussian Blur Image

<img width="190" height="268" alt="image" src="https://github.com/user-attachments/assets/8f49e1c2-015e-40f4-bf05-6563621bacb7" />

  
- Median Blur Image

<img width="272" height="272" alt="image" src="https://github.com/user-attachments/assets/deb07631-1444-4f79-915a-a25f83496c55" />


- Laplacian Kernel Image

<img width="201" height="280" alt="image" src="https://github.com/user-attachments/assets/135291d1-492f-42ea-adbd-508009fa02b6" />


- Laplacian Operator Image

  <img width="192" height="277" alt="image" src="https://github.com/user-attachments/assets/4b999a2f-0006-4c39-a1e3-c05e51743bd4" />


## Result

Thus, smoothing filters and sharpening filters were successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
