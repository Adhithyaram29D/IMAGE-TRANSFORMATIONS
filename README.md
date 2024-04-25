# IMAGE-TRANSFORMATIONS
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: 
Import the necessary libraries and read the original image and save it as a image variable.
<br>

### Step2:
Translate the image using a function warpPerpective()
<br>

### Step3:
Scale the image by multiplying the rows and columns with a float value.
<br>

### Step4:
Shear the image in both the rows and columns.
<br>

### Step5:
Find the reflection of the image.
<br>

## Program:
```python
Developed By: ADHITHYARAM D
Register Number: 212222230008
i)Image Translation
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image=cv2.imread("Photo.jpg")
input_image=cv2.cvtColor(input_image, cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim=input_image.shape
M=np.float32([[1,0,50],  [0,1,100],  [0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()
```

ii) Image Scaling
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("Photo.jpg")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
M = np.float32([[1.5,0,0],[0,1.7,0],[0,0,1]])
scaled_img = cv2.warpPerspective(org_image,M,(cols*2,rows*2))
plt.imshow(org_image)
plt.show()
```
iii)Image shearing
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("Photo.jpg")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
M_X = np.float32([[1,0.5,0],[0,1,0],[0,0,1]])
M_Y = np.float32([[1,0,0],[0.5,1,0],[0,0,1]])
sheared_img_xaxis = cv2.warpPerspective(org_image,M_X,(int(cols*1.5),int(rows*1.5)))
sheared_img_yaxis = cv2.warpPerspective(org_image,M_Y,(int(cols*1.5),int(rows*1.5)))
plt.imshow(sheared_img_xaxis)
plt.show()
plt.imshow(sheared_img_yaxis)
plt.show()
```
iv)Image Reflection
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("Photo.jpg")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
M_X = np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
M_Y = np.float32([[-1,0,cols],[0,1,0],[0,0,1]])
reflected_img_xaxis = cv2.warpPerspective(org_image,M_X,(int(cols),int(rows)))
reflected_img_yaxis = cv2.warpPerspective(org_image,M_Y,(int(cols),int(rows)))
plt.imshow(reflected_img_xaxis)
plt.show()
plt.imshow(reflected_img_yaxis)
plt.show()
```
v)Image Rotation
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
in_img=cv2.imread("Photo.jpg")
in_img=cv2.cvtColor(in_img,cv2.COLOR_BGR2RGB)
rows,cols,dim=in_img.shape
angle=np.radians(10)
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],
              [np.sin(angle),np.cos(angle),0],
              [0,0,1]])
rotated_img=cv2.warpPerspective(in_img,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotated_img)
plt.show()
```
vi)Image Cropping
```python
import numpy as np
import cv2
import matplotlib.pyplot as plt
org_image = cv2.imread("Photo.jpg")
org_image = cv2.cvtColor(org_image,cv2.COLOR_BGR2RGB)
plt.imshow(org_image)
plt.show()
rows,cols,dim = org_image.shape
cropped_img=org_image[80:900,80:500]
plt.imshow(cropped_img)
plt.show()
```
## Output:
### Input Image:
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/35b17489-2eff-4b37-aa6a-5fc10123b25d" width="200" height= "200">

### i)Image Translation
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/4f65c597-fc9b-4e73-bef8-1ab40a0f0f53" width="200" height= "200">
<br>

### ii) Image Scaling
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/b8e4bb0f-4f3b-4ce1-b3b5-a96b5faebe3a" width="200" height= "200">
<br>

### iii)Image shearing
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/ec803ebc-5516-4686-9876-6b479c115dce" width="200" height= "200">
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/bffdfd9f-50f0-4144-aa23-5a23f537e61d" width="200" height= "200">
<br>

### iv)Image Reflection
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/e83d6aad-a9aa-4662-8f1b-d739fad70d9c" width="200" height= "200">
<br>
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/1643fbd0-4d70-48cb-a80a-0e6971c56d75" width="200" height= "200">
<br>

### v)Image Rotation
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/b936d4ed-b843-4fef-95f3-022960a4e44c" width="200" height= "200">
<br>

### vi)Image Cropping
<img src = "https://github.com/Adhithyaram29D/IMAGE-TRANSFORMATIONS/assets/119393540/fea6a802-8796-43ca-a214-40e3c44e6a93" width="200" height= "200">
<br>
  
## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
