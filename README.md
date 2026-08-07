# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

- Name:Janani saraswathi S 
- Register No: 212225230110

Sobel Edge Detector:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('lion.jpeg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
Prewitt Edge Detector:
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
Roberts Edge Detector:
```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
Laplacian Edge Detector:
```
canny_edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
```
Canny Edge Detector:
```
image = cv2.imread("lion.jpeg")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(canny_edges, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')

```

---

## Output:
### original image :
<img width="697" height="456" alt="Screenshot 2026-08-07 111600" src="https://github.com/user-attachments/assets/c1f514c5-daae-4f05-86a4-cc09ca18ca18" />

### Sobel edge detection:
<img width="688" height="447" alt="Screenshot 2026-08-07 111629" src="https://github.com/user-attachments/assets/1b322a26-07a1-490b-9069-7d31032a8270" />

### Laplacian edge detection:
<img width="698" height="430" alt="Screenshot 2026-08-07 111655" src="https://github.com/user-attachments/assets/183527b2-9f8d-49a4-b8a9-f45b73fa88d3" />

### Canny edge detection:
<img width="687" height="445" alt="Screenshot 2026-08-07 111726" src="https://github.com/user-attachments/assets/7b116d93-e6d0-4d0f-a2c1-2bc42a002e5d" />


### Prewitt edge detection:
<img width="652" height="445" alt="image" src="https://github.com/user-attachments/assets/99a7afb7-1b38-465e-9089-659b31784eeb" />


---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
