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
### Developed By: K.M.SWETHA
### Register Number: 212221240055


## Output:

### i) Read and display the image
```Python
import cv2
image=cv2.imread('dipimage.jpg',1)
cv2.imshow('Swetha',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipimage](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/0a834a8c-71c5-497f-84f9-8a211f576293)
### Resized Image
```python
image=cv2.resize(image,(350,350))
cv2.imshow('Swetha',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![resized](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/960cb6e8-4391-45ee-96ed-056fc840941d)
### ii)Write the image

```python
import cv2
image=cv2.imread('dipimage.jpg',0)
cv2.imwrite('Swetha.jpg',image)
```
![dipexp1-opcode1](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/715f497f-6ea1-4066-b0bf-4a3af49d59b1)



### iii)Shape of the Image
```python
import cv2
image=cv2.imread('dipimage.jpg',1)
print(image.shape)
```
![dipexp1-opcode2](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/73f3a6ec-e23f-40a6-a93c-621e36bfe60e)

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('dipimage.jpg',1)
image=cv2.resize(image,(350,350))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,555),
                    random.randint(0,555),
                    random.randint(0,555)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipexp1-opimg1](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/0aa905ab-6625-491d-82c1-62790c866cc1)


### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('dipimage.jpg',1)
image=cv2.resize(image,(350,350))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipexp1-opimg2](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/9cfa2145-9356-4c69-a54e-2c960ac8b48a)

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('dipimage.jpg',1)
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
![dipexp1-opimg3](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/3d118788-e19c-4da0-86dd-310f660384eb)


### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('dipimage.jpg')
img = cv2.resize(img,(350,350))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipexp1-opimg4](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/8ce4b83c-a632-482d-aa9b-0cc08250461d)

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('dipimage.jpg')
img = cv2.resize(img,(350,350))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipexp1-opimg5](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/37deb70f-bf9a-4d96-875c-7bbd55ef81ac)

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('dipimage.jpg',1)
img = cv2.resize(img,(370,370))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipexp1-opimg6](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/8f5e492c-52cf-497b-bf66-57eabbc7938d)

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("dipimage.jpg",1)
img = cv2.resize(img,(370,370))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![dipexp1-opimg7](https://github.com/swethamohanraj/COLOR_CONVERSIONS_OF-IMAGE/assets/94228215/b7332852-7302-4204-bd09-c83c522702f4)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







