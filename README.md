# Edge-Linking-using-Hough-Transform
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
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:
```Python

# Read image and convert it to grayscale image
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('road.jpg',0)
img= cv2.GaussianBlur(image1,(3,3),0)
plt.imshow(img)
# Find the edges in the image using canny detector and display
edges1 = cv2.Canny(img,100,200)
plt.imshow(edges1,cmap = 'gray')
plt.title('Edge Image'), plt.xticks([]), plt.yticks([])
plt.show()
# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(edges1,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)
# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(edges1,(x1, y1),(x2, y2),(255, 0, 0),3)
# Display the result
plt.imshow(edges1)
```
## Output

### Input image and grayscale image
![cv1](https://user-images.githubusercontent.com/75235402/169012824-2f6a703d-996e-44fc-a9c7-915b3800f4ce.jpg)


### Canny Edge detector output
![cv2](https://user-images.githubusercontent.com/75235402/169012858-d4acbbba-d5c7-4f5e-9f8b-e4ace9d0d037.jpg)

### Display the result of Hough transform
![cv3](https://user-images.githubusercontent.com/75235402/169012890-9a94dfdd-1a8c-4ba7-90c7-6e371c2f9794.jpg)


## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
