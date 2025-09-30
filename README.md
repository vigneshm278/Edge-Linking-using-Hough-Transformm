# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program:
```
Name: Vignesh M
Reg no: 212223240176

i: Input image and grayscale image

import numpy as np
import cv2
import matplotlib.pyplot as plt

gray = cv2.imread('nature.jpg', cv2.IMREAD_GRAYSCALE)
img_color = cv2.imread('nature.jpg', cv2.IMREAD_COLOR)
img_c = cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB)
gray_rgb = cv2.cvtColor(gray, cv2.COLOR_GRAY2RGB)

gray = cv2.GaussianBlur(gray, (3, 3), 0)

plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
plt.imshow(gray_rgb, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()

ii: Canny Edge detector output

canny = cv2.Canny(gray, 120, 150)

plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()


iii: Display the result of Hough transform

lines = cv2.HoughLinesP(canny, 1, np.pi/180, threshold=80, minLineLength=50, maxLineGap=250)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)

plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```
## Output:

### Input image and grayscale image
<img width="251" height="411" alt="download" src="https://github.com/user-attachments/assets/bdcd70ee-4f73-4051-a448-44ffaad65af6" />
<img width="251" height="411" alt="download" src="https://github.com/user-attachments/assets/1dd244d0-87aa-44a2-86fb-a92b2e204e9e" />


### Canny Edge detector output
<img width="251" height="411" alt="download" src="https://github.com/user-attachments/assets/8af5ea23-e1b9-4ad3-b8f9-e1d58c043dad" />



### Display the result of Hough transform
<img width="251" height="411" alt="download" src="https://github.com/user-attachments/assets/0ca82fc0-9a9b-4adb-a0ab-7d80e52e0616" />
### Result:
Thus, the image has been successfully converted.
