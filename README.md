# Histogram and Histogram Equalization of an image
## AIM:
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## SOFTWARE REQUIRED:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary libraries and read two images, Color image and Gray Scale image.
### Step 2:
Calculate the Histogram of Gray scale image and any one channel of the color image.
### Step 3:
Display the histograms.
### Step 4:
Equalize the grayscale image.
### Step 5:
Display the equalized grayscale image.

## Program:
```python
# Developed By: U.BHAVYA
# Register Number: 212220230055

import cv2
import matplotlib.pyplot as plt
Gray_image=cv2.imread('orange.jpg')
plt.imshow(Gray_image)
plt.show()
Color_image=cv2.imread('berry.jpg')
plt.imshow(Color_image)
plt.show()

# Write your code to find the histogram of gray scale image and color image channels.

hist=cv2.calcHist([Gray_image],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("gray_scale value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image

hist1=cv2.calcHist([Color_image],[1],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("color_scale value")
plt.ylabel("pixel count")
plt.stem(hist1)
plt.show()

# Write the code to perform histogram equalization of the image. 

equ=cv2.equalizeHist(cv2.imread('berry.jpg',0))
equ=cv2.cvtColor(equ,cv2.COLOR_BGR2RGB)
plt.title("Equalised Image")
plt.axis("off")
plt.imshow(equ)
plt.show()

```
## Output:
### Input Grayscale Image and Color Image

![image](https://user-images.githubusercontent.com/75235293/165235029-f44cb349-8ac2-43d2-9805-b05bff4ee774.png)
![image](https://user-images.githubusercontent.com/75235293/165235096-9fec778e-78fe-4844-aca2-4d578efeda50.png)

### Histogram of Grayscale Image and any channel of Color Image

![image](https://user-images.githubusercontent.com/75235293/165235183-89311cea-ea27-492e-a273-7ee6153aa566.png)
![image](https://user-images.githubusercontent.com/75235293/165235230-fed8dd82-508c-483d-a45a-a0c0c30a8975.png)

### Histogram Equalization of Grayscale Image

![image](https://user-images.githubusercontent.com/75235293/165235269-e8a57c72-3e3c-4f43-9260-09668eaa3b17.png)


## Result:

Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
