# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read two images, Color image and Gray Scale image.
### Step2:
Calculate the Histogram of Gray scale image and each channel of the color image.
### Step3:
Display the histograms with their respective images.
### Step4:
Equalize the grayscale image.
### Step5:
Display the grayscale image.

## Program:
```python
# Developed By:Kumaran.B
# Register Number:212220230026
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.
gi=cv2.imread("ch.jpg",0)
ci=cv2.imread("house.jpg")
gi=cv2.resize(gi,(500,400))
ci=cv2.resize(ci,(500,400))
cv2.imshow("gi",gi)
cv2.imshow("ci",ci)
cv2.waitKey(0)
cv2.destroyAllWindows()


# Display the histogram of gray scale image and any one channel histogram from color image
hist=cv2.calcHist([gi],[0],None,[256],[0,255])
hist1=cv2.calcHist([ci],[2],None,[256],[0,255])
plt.figure()
plt.title("grey image")
plt.xlabel("greyscale value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()
plt.figure()
plt.title("color image")
plt.xlabel("colorscale value")
plt.ylabel("pixel count")
plt.stem(hist1)
plt.show()


# Write the code to perform histogram equalization of the image. 
equ=cv2.equalizeHist(gi)
cv2.imshow("gi",gi)
cv2.imshow("df",equ)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Input Grayscale Image and Color Image
![Screenshot (69)](https://user-images.githubusercontent.com/75243072/164030173-9e8b5be2-3018-40f6-9840-051f853f0b94.png)


### Histogram of Grayscale Image and any channel of Color Image
![Screenshot (67)](https://user-images.githubusercontent.com/75243072/164030416-40aca359-c367-46ba-9871-2eafa38f7088.png)
![Screenshot (68)](https://user-images.githubusercontent.com/75243072/164030449-5ffaf1b2-0c20-4d9b-a0dc-69d2878fddb8.png)


### Histogram Equalization of Grayscale Image
![Screenshot (70)](https://user-images.githubusercontent.com/75243072/164030510-1992a623-fd67-461b-8035-fc97c72b6fe0.png)


## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
