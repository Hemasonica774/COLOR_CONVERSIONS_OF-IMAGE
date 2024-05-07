# EX NO-1
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

### Program:
### Developed By:P.Hemasonica
### Register Number: 212222230048


## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('hema.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('hems',image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```

![Screenshot 2024-05-07 113357](https://github.com/Hemasonica774/COLOR_CONVERSIONS_OF-IMAGE/assets/118361409/49d3dd5a-569f-4f33-85f3-7728c4ac5ce5)


### ii)Write the image
```
import cv2
image=cv2.imread('hema.jpg',0)
cv2.imwrite('test.jpg',image)

```
![Screenshot 2024-05-07 113751](https://github.com/Hemasonica774/COLOR_CONVERSIONS_OF-IMAGE/assets/118361409/6e3b9969-44e5-46ed-8410-f6dc682918ed)



### iii)Shape of the Image
```
import cv2
image=cv2.imread('hema.jpg')
print(image.shape)\

```
![Screenshot 2024-05-07 113838](https://github.com/Hemasonica774/COLOR_CONVERSIONS_OF-IMAGE/assets/118361409/32860709-033d-4dbf-b1e3-6771eaf2646c)



### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('tree.png',1)
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
![Screenshot 2024-02-21 185707](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/37ad4393-326c-413b-a714-c31fe4691ca1)

### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('tree.png',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-02-21 185725](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/c067c100-35ff-45df-9a2c-47989b6a0548)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('tree.png',1)
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
![Screenshot 2024-02-21 185755](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/672b5c9e-76be-4af9-a45c-ece3ffe2e428)

### vii) HSV to RGB and BGR
```
img = cv2.imread('tree.png')
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
![Screenshot 2024-02-21 185820](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/ab92f371-f9d9-4d5a-a98b-3a7bde7f14a4)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('tree.png')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-02-21 185837](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/946dcf55-3986-4c38-b7b1-7feeccf3342a)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('tree.png',1)
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
![Screenshot 2024-02-21 185858](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/dad1d471-b3b8-452c-bc29-7fb03fcd5fde)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("tree.png",1)
img = cv2.resize(img,(200,200))
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
![Screenshot 2024-02-21 185920](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/56dae9ee-70dc-46fd-ac9f-05aa6d16f635)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







