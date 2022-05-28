# Image-Transformation
## AIM:
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step1:
Import the required libraries and read the original image.

### Step2:
Translate the image.

### Step3:
Scale the image.

### Step4:
Shear the image.

### Step5:
Find reflection of image.

### Step 6:
Rotate the image.

### Step 7:
Crop the image.

### Step 8:
Display all the Transformed images.

## PROGRAM:
```python
# Developed By: Aashima Nazreen Sayeed S
# Register Number: 212221240002

import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("penguin.jpg")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim = input_image.shape

# i)Image Translation
M = np.float32([[1,0,100],
               [0,1,200],
               [0,0,1]])
translated_image = cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()

# ii) Image Scaling
M = np.float32([[1.5,0,0],
               [0,1.8,0],
               [0,0,1]])
scaled_image = cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
plt.imshow(scaled_image)
plt.show()

# iii)Image shearing
M_x = np.float32([[1,0.5,0],
                 [0,1,0],
                 [0,0,1]])
M_y = np.float32([[1,0,0],
                 [0.5,1,0],
                 [0,0,1]])
sheared_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols*1.5),int(rows*1.5)))
sheared_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
plt.imshow(sheared_xaxis)
plt.show()
plt.axis('off')
plt.imshow(sheared_yaxis)
plt.show()

# iv)Image Reflection
M_x = np.float32([[1,0,0],
                 [0,-1,rows],
                 [0,0,1]])
M_y = np.float32([[-1,0,cols],
                 [0,1,0],
                 [0,0,1]])
reflected_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols),int(rows)))
reflected_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(reflected_xaxis)
plt.show()
plt.axis('off')
plt.imshow(reflected_yaxis)
plt.show()

# v)Image Rotation
angle = np.radians(30)
M = np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotated_image = cv2.warpPerspective(input_image,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotated_image)
plt.show()

# vi)Image Cropping
cropped_image = input_image[100:300,100:300]
plt.axis('off')
plt.imshow(cropped_image)
plt.show()

```
## OUTPUT:
### Original Image: 
![ori](https://user-images.githubusercontent.com/93427086/165988186-c3d11058-2c17-48c7-8925-bd2de2439271.png)
<br>

### i)Image Translation:
![translation](https://user-images.githubusercontent.com/93427086/165988202-f0ded418-8939-4484-a32d-f81a8dab4c0f.png)
<br>

### ii) Image Scaling:
![scaling](https://user-images.githubusercontent.com/93427086/165988219-586780ca-e2a3-4006-be9f-3d2d7f8d6df2.png)
<br>

### iii)Image shearing:
![shearing](https://user-images.githubusercontent.com/93427086/165988235-7f00eff1-9655-40b8-aab6-9dcf6501a890.png)
<br>


### iv)Image Reflection:
![reflection](https://user-images.githubusercontent.com/93427086/165988261-7149212d-d11f-453a-b90c-b1f38d9bd7c7.png)
<br>

### v)Image Rotation:
![rotation](https://user-images.githubusercontent.com/93427086/165988286-62aa933f-995a-472b-9346-0c21eb007b8f.png)
<br>

### vi)Image Cropping
![cropping](https://user-images.githubusercontent.com/93427086/165988299-49874069-825c-4032-ab97-4bcdea922d04.png)
<br>


## RESULT: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
