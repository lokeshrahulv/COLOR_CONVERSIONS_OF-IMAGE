# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: LOKESH RAHUL V V 
### Register Number: 212222100024


## Output:

### i) Read and display the image
```python
    import cv2
    image=cv2.imread('img.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('Lokesh Rahul',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-02-15 202820](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/7505a83d-0791-47fb-ae40-7e84d23351fb)

### ii)Write the image
```python
    import cv2
    image=cv2.imread('img.jpg',0)
    cv2.imwrite('d.jpg',image)
```
### Output:
![Screenshot 2024-02-15 202951](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/c0cb2d35-8ae8-49bd-a14f-d713ef7c9339)

### iii)Shape of the Image
```python
    import cv2
    image=cv2.imread('img.jpg',1)
    print(image.shape)
```
### Output:
![Screenshot 2024-02-15 203101](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/ddfa1d9a-e446-4df8-81bf-31c34a0e2d12)

### iv)Access rows and columns
```python
   
from google.colab.patches import cv2_imshow
import random
import cv2
image=cv2.imread('img.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
  for j in range(image.shape[1]):
    image[i][j]=[random.randint(0,255),random.randint(0,255),random.randint(0,255)] 
cv2_imshow(image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output
![Screenshot 2024-02-15 203154](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/c88ab03d-c02f-4c00-bb53-0cf3d9427f23)

### v)Cut and paste portion of image
```python
from google.colab.patches import cv2_imshow
import cv2
import numpy as np
image=cv2.imread('img.jpg',1)
image = cv2.resize(image, (400, 400))
print(image.shape)
tag =image[130:200,110:190]
image[110:180,120:200] = tag
cv2_imshow(image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-02-15 203322](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/63d5ebf3-a69b-4916-87f7-4a9c5c2c0054)

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('img.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-02-15 204403](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/9a01b46c-c74a-47ec-99ac-d07aaf82b460)
![Screenshot 2024-02-15 204438](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/7bb0c3d7-fd3c-4f91-bed9-83ef1aa00fb0)
![Screenshot 2024-02-15 204438](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/0a4629ff-0516-4369-b6bd-f4adb1244a06)
![Screenshot 2024-02-15 204508](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/6f19c7d5-b682-44f1-a1e2-49f8eb0dca1f
![Screenshot 2024-02-15 204508](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/e2234b55-936e-4642-a619-2ac1ad02f081)

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('img.jpg')
img = cv2.resize(img,(300,200))
img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2_imshow(img)
RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2_imshow(RGB)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2_imshow(BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
###Output:
![Screenshot 2024-02-15 203510](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/480a465f-c7ea-4717-a22c-723f9503895f)

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('img.jpg')
img = cv2.resize(img,(300,200))
cv2_imshow(img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2_imshow(YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2_imshow(YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-02-15 203726](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/aa2ea77d-3acd-47e5-8372-e32f1a0a838a)

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('img.jpg',1)
img = cv2.resize(img,(300,200))
R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]
cv2_imshow(R)
cv2_imshow(G)
cv2_imshow(B)
merged = cv2.merge((B,G,R))
cv2_imshow(merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-02-15 204007](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/e0c37b2c-0327-4403-b2e9-e651fc19f7f7)


### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("img.jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
H,S,V=cv2.split(img)
cv2_imshow(H)
cv2_imshow(S)
cv2_imshow(V)
merged = cv2.merge((H,S,V))
cv2_imshow(merged)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![Screenshot 2024-02-15 203936](https://github.com/lokeshrahulv/COLOR_CONVERSIONS_OF-IMAGE/assets/118423842/c4f651c4-864e-406b-babb-5a0e9c90c5b9)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







