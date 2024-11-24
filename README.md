
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

<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```
import cv2
image=cv2.imread('unnamed.jpg')
image=cv2.resize(image,(400,300))
cv2.imshow('Image Window',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
 ```
  </td>
  <td>

### OUTPUT:
![unnamed](https://github.com/user-attachments/assets/80bcc385-14b5-462a-a782-4ac505218ec4)



  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```
import cv2
image=cv2.imread('unnamed.jpg',0)
cv2.imwrite('demos.jpg',image)
```
  </td>
  <td>

### OUTPUT:
<img width="342" alt="Screenshot 2024-09-11 at 9 02 13 AM" src="https://github.com/user-attachments/assets/46f2bc0f-c7a8-4795-a6da-7c6bc6f6d43e">


  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```
import cv2
image=cv2.imread('unnamed.jpg',1)
print(image.shape)
```
  </td>
  <td>

### OUTPUT:
<img width="312" alt="Screenshot 2024-09-11 at 9 02 27 AM" src="https://github.com/user-attachments/assets/ab01b93e-940a-4edc-8fff-90e768511f8c">




  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```
 import random
import cv2
image=cv2.imread('unnamed.jpg',1)
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
  </td>
  <td width="50%">

### OUTPUT:
<img width="400" alt="Screenshot 2024-09-11 at 9 03 53 AM" src="https://github.com/user-attachments/assets/836aa747-41d3-4388-8a1a-c827d087f724">



  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('unnamed.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[130:200,110:190]
image[110:180,120:200] = tag
cv2.imshow('partimage1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
  </td>
  <td>
    
### OUTPUT:

<img width="401" alt="Screenshot 2024-09-11 at 9 04 49 AM" src="https://github.com/user-attachments/assets/024ba640-96f7-4df8-a4cb-32648d0be2d4">



  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('unnamed.jpg',1)
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

### OUTPUT:
<img width="1440" alt="Screenshot 2024-09-11 at 9 10 33 AM" src="https://github.com/user-attachments/assets/4b49f722-591b-4b52-910e-29399ca23b79">





### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('unnamed.jpg')
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

### OUTPUT:
<img width="902" alt="Screenshot 2024-09-11 at 9 12 38 AM" src="https://github.com/user-attachments/assets/f382f1b9-b4e7-4b07-9981-aa319c8b1667">






### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('unnamed.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:


<img width="904" alt="Screenshot 2024-09-11 at 9 13 35 AM" src="https://github.com/user-attachments/assets/af6f4383-7785-4ec5-bfcb-660a34d65900">


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('unnamed.jpg',1)
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

### OUTPUT:
<img width="1207" alt="Screenshot 2024-09-11 at 9 18 53 AM" src="https://github.com/user-attachments/assets/805eca07-edb3-4c68-a9b7-1f0d5563ecb7">






### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("unnamed.jpg",1)
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

### OUTPUT:

<img width="1207" alt="Screenshot 2024-09-11 at 9 20 40 AM" src="https://github.com/user-attachments/assets/03a173c9-097f-41e1-abf0-d93f273478c7">

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







