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

##### Program:
### Developed By:S.Prema Latha
### Register Number: 212222230112

## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('prema.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('rose',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-05-07 103333](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/7090459a-615f-491d-999d-86e669e891f0)



### ii)Write the image
```
import cv2
image=cv2.imread('prema.jpg',0)
cv2.imwrite('test.jpg',image)
```

![Screenshot 2024-05-07 104511](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/0d019cd4-eb0a-4412-8cb1-5a8f49095755)



### iii)Shape of the Image
```
import cv2
image=cv2.imread('prema.jpg')
print(image.shape)
```

![Screenshot 2024-05-07 104515](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/55efa5b7-f836-4706-b6bf-bb3a9c942ab9)




### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('prema.jpg',1)
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
![Screenshot 2024-05-07 103529](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/aad97e7c-e3a4-46b9-8967-c274b0754a9d)




### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('prema.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![Screenshot 2024-05-07 103615](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/c67782f3-2e6d-4472-9aec-71eb9f62e717)




### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('prema.jpg',1)
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
![Screenshot 2024-05-07 103655](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/b81eaf46-9ef1-4752-94c8-0f6f575ca643)



### vii) HSV to RGB and BGR
```
img = cv2.imread('prema.jpg')
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
![Screenshot 2024-05-07 103754](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/88520bdd-eca9-4f62-a392-3f6df58b15b0)



### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('prema.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-05-07 103826](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/5b2b018c-c538-4c85-8104-f641d325dd0b)




### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('prema.jpg',1)
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


![Screenshot 2024-05-07 103856](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/d1b29e00-a1cf-435f-9bb0-2473db1effbf)




### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("prema.jpg",1)
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

![Screenshot 2024-05-07 103923](https://github.com/premalatha-sureshbabu/COLOR_CONVERSIONS_OF-IMAGE/assets/120620842/0cf43c3e-0aa5-45d4-96cd-4e018f3407fc)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







