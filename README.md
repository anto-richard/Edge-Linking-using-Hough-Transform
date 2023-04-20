# Edge-Linking-using-Hough-Transform...

## Aim:

To write a Python program to detect the lines using Hough Transform.

## Software Required:

Anaconda - Python 3.7 .

## Algorithm:

### Step 1:

Import all the necessary packages required for the program.

### Step 2:

Load a image using imread() from cv2 module.

### Step 3:

Convert the image to grayscale image.

### Step 4:

Using Canny edge operator from cv2, detect the edges of the image.

### Step 5:

Using the HoughLinesP(), detect the line co-ordinates for every points in the images. Using For loop, draw the lines on the found co-ordinates.

### Step 6:

Display the image found by the HoughLinesP() and end the program.

## Program:

```python

# Read image and convert it to grayscale image:

import numpy as np
import matplotlib.pyplot as plt
import cv2
image = cv2.imread("twin-towers.jpg",0)
img = cv2.GaussianBlur(image,(3,3),0)
plt.axis('off')
plt.imshow(img)
plt.show()

```

```python

# Find the edges in the image using canny detector and display:

edge = cv2.Canny(img,50,100)
plt.imshow(edge,cmap='gray')
plt.title('Edged Image after applying Canny Edge Detector')
plt.xticks([])
plt.yticks([])
plt.show()

```

```python

# Detect points that form a line using HoughLinesP:

lines=cv2.HoughLinesP(edge,1,np.pi/180, threshold=80, minLineLength=50,maxLineGap=250)

```

```python

# Draw lines on the image:

for line in lines:
    x1,y1,x2,y2 = line[0]
    cv2.line(edge,(x1,y1),(x2,y2),(250,0,0),3)
    
```

```python

# Display the result:

plt.imshow(edge)
plt.axis('off')
plt.show()

```

## Output:

### Input image:

![twin-towers](https://user-images.githubusercontent.com/93427534/233144762-c5ce1b82-82d2-42db-9bae-58913090bd80.jpg)

### Grayscale image:

![out1](https://user-images.githubusercontent.com/93427534/233145958-5305b595-20f2-4f60-b7fc-174b74ec48b3.png)

### Canny Edge detector output:

![out2](https://user-images.githubusercontent.com/93427534/233145966-b57a8fb2-ee3e-4acc-b12f-5ef64959367e.png)

### Display the result of Hough transform:

![out3](https://user-images.githubusercontent.com/93427534/233145980-057a2dbe-8d54-4a7a-bbb3-c154c81737ff.png)

## Result:

Thus the program is written with python and OpenCV to detect lines using Hough transform.

