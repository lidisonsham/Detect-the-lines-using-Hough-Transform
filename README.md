# Record-HOUGH-TRANSFORM
# Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

Learning Objective Understand each stage of image processing Learn how to build a complete computer vision pipeline Practice writing code in guided sections

# Software Used
Anaconda – Python 3.7 Jupyter Notebook / VS Code OpenCV (cv2) NumPy Matplotlib

# Algorithm & Explanation
Step 1: Import Libraries Step 2: Read the Image Step 3: Convert to Grayscale Step 4: Display Images Step 5: Thresholding threshold = Step 6: Region of Interest (ROI) Step 7: Edge Detection (Canny) Step 8: Gaussian Blur Step 9: Hough Transform Step 10: Lane Detection Logic

# program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread(r"C:\Users\acer\Pictures\Screenshots\LUDO.png")
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

# output
<img width="395" height="411" alt="image" src="https://github.com/user-attachments/assets/6aa458ad-0ded-4409-9d8d-50b3b2c45afa" />
<img width="396" height="420" alt="image" src="https://github.com/user-attachments/assets/6349e3f7-de99-414a-9794-ce435fe9ea2e" />
<img width="406" height="423" alt="image" src="https://github.com/user-attachments/assets/46e4adaf-a79b-482a-bd56-603ec5ec6ec6" />
<img width="396" height="416" alt="image" src="https://github.com/user-attachments/assets/b942f234-d4ce-44ec-929b-bb031bc08c28" />




# Result
Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.
