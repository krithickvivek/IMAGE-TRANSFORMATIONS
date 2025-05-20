# IMAGE-TRANSFORMATIONS

## Aim:
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules

### Step2:
Choose an image and save it as filename.jpg

### Step3:
Use imread to read the image

### Step4:
Use cv2.warpPerspective(image,M,(cols,rows)) to translation the image

### Step5:
Use cv2.warpPerspective(image,M,(cols2,rows2)) to scale the image

### Step6:
Use cv2.warpPerspective(image,M,(int(cols1.5),int(rows1.5))) for x and y axis to shear the image

### Step7:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) for x and y axis to reflect the image

### Step8:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) to rotate the image

### Step9:
Crop the image to remove unwanted areas from an image

### Step10:
Use cv2.imshow to show the image

## Program:
### Developed By: Krithick Vivekananda 
### Register Number: 212223240075
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

input_image=cv2.imread("img0.jpg")
input_image=cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
print("Input Image:")
plt.imshow(input_image)
plt.show()
```
#### i)Image Translation
```python
rows,cols,dim=input_image.shape
M=np.float32([[1,0,100],[0,1,200],[0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
print("Image Translation:")
plt.imshow(translated_image)
plt.show()
```
#### ii) Image Scaling
```python
rows,cols,dim=input_image.shape
M=np.float32([[1.5,0,0],[0,1.8,0],[0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
print("Image Scaling:")
plt.imshow(translated_image)
plt.show()
```
#### iii)Image shearing
```python
rows,cols,dim=input_image.shape
M1=np.float32([[1,0.5,0],[0,1,0],[0,0,1]])
M2=np.float32([[1,0,0],[0.5,1,0],[0,0,1]])
translated_image1=cv2.warpPerspective(input_image,M1,(int(cols*1.5),int(rows*1.5)))
translated_image2=cv2.warpPerspective(input_image,M2,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
print("Image Shearing:")
plt.imshow(translated_image1)
plt.imshow(translated_image2)
plt.show()
```
#### iv)Image Reflection
```python
rows,cols,dim=input_image.shape
M1=np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
M2=np.float32([[-1,0,cols],[0,1,0],[0,0,1]])
translated_image1=cv2.warpPerspective(input_image,M1,(int(cols),int(rows)))
translated_image2=cv2.warpPerspective(input_image,M2,(int(cols),int(rows)))
plt.axis('off')
print("Image Reflection:")
plt.imshow(translated_image1)
plt.imshow(translated_image2)
plt.show()
```
#### v)Image Rotation
```python
rows,cols,dim=input_image.shape
angle=np.radians(10)
M=np.float32([[np.cos(angle),-(np.sin(angle)),0],[np.sin(angle),np.cos(angle),0],[0,0,1]])
translated_image=cv2.warpPerspective(input_image,M,(int(cols),int(rows)))
plt.axis('off')
print("Image Rotation:")
plt.imshow(translated_image)
plt.show()
```
#### vi)Image Cropping
```python
import cv2
import matplotlib.pyplot as plt
image = cv2.imread("img0.jpg")
h, w, _ = image.shape
cropped_face = image[int(h*0.2):int(h*0.8), int(w*0.3):int(w*0.7)]
cv2.imwrite("cropped_pigeon_face.jpg", cropped_face)
plt.imshow(cv2.cvtColor(cropped_face, cv2.COLOR_BGR2RGB))
print("Image Cropping:")
plt.axis("off")
plt.show()
```
## Output:
![image](https://github.com/user-attachments/assets/929d4fa3-264c-4c37-976c-d6d2092963df)

### i)Image Translation
![image](https://github.com/user-attachments/assets/8faa36e7-29dd-4cad-bad7-d4be9d634ac4)

### ii) Image Scaling
![image](https://github.com/user-attachments/assets/e85eb150-ce80-4ab5-bb50-d27174c296b1)

### iii)Image shearing
![image](https://github.com/user-attachments/assets/497f6dc9-6948-4317-a9e4-8bc28f56acd3)

### iv)Image Reflection
![image](https://github.com/user-attachments/assets/e064277d-4875-4c56-9c9b-8f224aed5ce8)

### v)Image Rotation
![image](https://github.com/user-attachments/assets/3499a0be-e892-4e93-8611-901a6b07e54b)

### vi)Image Cropping
![image](https://github.com/user-attachments/assets/d2d9477f-b2c9-4a45-9395-98f97e9ed7ee)

## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
