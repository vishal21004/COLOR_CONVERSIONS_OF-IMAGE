
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
```
### Developed By: Divakar R
### Register Number:212222240026
```
## Program:
### i) Read and display the image
```python
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(300,300))
cv2.imshow('DISPLAY',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![og](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/101c60d5-2b92-4e87-9eb1-2d0886b93b67)


<br>

### ii)Write the image
```python
image=cv2.imread('image.jpg',0)
cv2.imwrite('Photo.jpg',image)
```
![write image](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/4d8ff1a8-1895-4b29-a484-0ee5435cc7cd)

<br>

### iii)Shape of the Image
```python
import cv2
image=cv2.imread('image.jpg',1)
print(image.shape)
```
![shapr image](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/3d367200-1822-4541-b456-3e3fc7024cad)


<br>

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                     random.randint(0,255),
                     random.randint(0,255)]
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```



<br>

### v)Cut and paste portion of image
```python
import cv2
image=cv2.imread('image.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


<br>

### vi) BGR and RGB to HSV and GRAY
```python
    import cv2
    img = cv2.imread('image.jpg',1)
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
![bgr to hsv](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/a6de26fc-c0dc-4291-83e4-cc78a5b05a25)
![bgr to gray](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/097f6e38-1de0-41d6-829d-bd8622ff01ba)
![rgb to hsv](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/ae8c46cc-1cb6-46f7-8916-04c741d08ed7)
![rgb to gray](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/9e253a11-0665-46de-9d2e-9d75d40ca9bc)



<br>

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![hsv to rgb](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/342ad1b1-c2b8-419c-b719-f7c37c332e7e)
![hsv to bgr](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/30193763-094c-4272-bb86-2c87b26c8642)


<br>

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('image.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```


<br>
![rgb to yrcrcb](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/81a2cf69-2c29-47d8-b192-9ea2ac8fc425)
![spl and mrg 1](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/1920fda4-8b47-455b-93a4-b03cd6f03a3a)

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('image.jpg',1)
img = cv2.resize(img,(300,200))

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
![spl and mrg 1](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/17f54e95-0419-424b-b8e5-cdbf44dc5f79)

<br>

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("image.jpg",1)
img = cv2.resize(img,(300,200))
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
![spl and mrg 2](https://github.com/vishal21004/COLOR_CONVERSIONS_OF-IMAGE/assets/119560110/f13aae8b-bfee-42ab-ae9e-fc98dc354e0b)


<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







