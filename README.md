### Developed By: Tharika S
### Register Number: 212222230159

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
### Step1: Choose an image and save it as a filename.jpg ,
### Step2: Use imread(filename, flags) to read the file.
### Step3: Use imshow(window_name, image) to display the image.
### Step4: Use imwrite(filename, image) to write the image.
### Step5: End the program and close the output image windows.
### Step6: Convert BGR and RGB to HSV and GRAY
### Step7: Convert HSV to RGB and BGR
### Step8: Convert RGB and BGR to YCrCb
### Step9: Split and Merge RGB Image
### Step10: Split and merge HSV Image

##### Program:

<table>
  <tr>
    <td width=50%>

### i) Read and display the image
```Python
    import cv2
    image=cv2.imread('loki.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.waitKey(0)
    cv2.destroyAllWindows()
``` 
  </td>
  <td>

### OUTPUT:
![image](https://github.com/user-attachments/assets/9ceebfab-9591-4e7e-a00f-71789bd6c3ff)





  </td>
  </tr>

   <tr>
    <td width=50%>

### ii)Write the image
```Python
    import cv2
    image=cv2.imread('loki.jpg',0)
    cv2.imwrite('loki1.jpg',image)
```
  </td>
  <td>

### OUTPUT:
![image](https://github.com/user-attachments/assets/7df35d9a-1de4-4318-a919-c9a05c949752)




  </td>
  </tr>
  <tr>
    <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('loki.jpg',1)
    print(image.shape)
```
  </td>
  <td>

### OUTPUT:
![image](https://github.com/user-attachments/assets/1cbd6af8-6285-49db-8e85-0b20271ceaea)



  </td>
  </tr>
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
    import random
    import cv2
    image=cv2.imread('loki.jpg',1)
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

![image](https://github.com/user-attachments/assets/06dd9406-98a1-41e6-ab1e-ea8915753788)


  </td>
  </tr>
  <tr>
    <td width=50%>
      
### v)Cut and paste portion of image

 ```Python
    import cv2
    image=cv2.imread('loki.jpg',1)
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
![image](https://github.com/user-attachments/assets/5fbeda91-4883-4edf-84aa-a6430a6aa592)


  </td>
  </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('loki.jpg',1)
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
![image](https://github.com/user-attachments/assets/053fe9c6-b61a-4ed5-817b-5e6566ee2a68)



### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('loki.jpg')
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
![image](https://github.com/user-attachments/assets/75dd5ef8-0763-44cd-8249-0cbda3da66c4)


### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('loki.jpg')
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
![image](https://github.com/user-attachments/assets/9b7df28c-1314-4912-bb5e-c09a6b23e9c4)



### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('loki.jpg',1)
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
![image](https://github.com/user-attachments/assets/ae437c97-44b0-458a-87da-3ce910cc0017)



### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("loki.jpg",1)
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
![image](https://github.com/user-attachments/assets/7e9e36cd-2230-4a9c-8d0f-c453bc97513f)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







