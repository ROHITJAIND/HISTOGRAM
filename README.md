# EX-4 Histogram and Histogram Equalization of an Image
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**DATE:** 05.09.2023
### Aim:
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.
### Software Required:
- Anaconda - Python 3.7
### Algorithm:
- Step1: Import cv2 and matplotlib.pyplot.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Developed By: ROHIT JAIN D
- Step2: Read and display the input images.&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Register Number: 212222230120
- Step3: Calculate the Histogram Values using calcHist().
- Step4: Display the histograms.
- Step5: Calculate and display the equalized image using equalizeHist().
### Program:
<table>
  <tr>
    <td width=50%>

#### Histogram of Gray scale image and Color image
```Python
import cv2
import matplotlib.pyplot as plt

cimg=cv2.imread('blue.jpg')
gimg=cv2.imread('gray.jpg')

plt.imshow(cimg)
plt.show()
plt.imshow(gimg)
plt.show()
```
</td>
<td>

  #### Output:
<img src="https://github.com/ROHITJAIND/HISTOGRAM/assets/118707073/d33379b7-6420-459f-86d1-8b6e44fbae1e">
</td>
</tr>
  </table>
<table>
  
<tr>
  <td>
  
#### Histogram of Gray scale & histogram from color image:
```Python
import cv2
import matplotlib.pyplot as plt

cimg=cv2.imread('blue.jpg')
gimg=cv2.imread('gray.jpg')

gray_hist=cv2.calcHist([gimg],[0],None,[256],[0,256])
color_hist=cv2.calcHist([cimg],[0],None,[256],[0,256])

plt.figure()
plt.title('Gray Image Histogram')
plt.xlabel('Grayscale Value')
plt.ylabel('Pixel Count')
plt.stem(gray_hist)
plt.show()

plt.title("One Color Histogram")
plt.xlabel("Color Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()
```
</td>
<td>
  
#### Output:
<img src="https://github.com/ROHITJAIND/HISTOGRAM/assets/118707073/351a0a7b-2e94-49c2-b89c-50ed5e96878f">
</td>
</tr>
  </table>
<table>
  
<tr>
  <td>
    
#### Histogram equalization of the Image 
```Python
import cv2
gimg=cv2.imread('gray.jpg',0)
gimg=cv2.resize(gimg,(300,200))

equ = cv2.equalizeHist(gimg)

cv2.imshow('Gray Image',gimg)
cv2.imshow('Equalized Image',equ)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
</td>
<td>

  #### Output:
<img src="https://github.com/ROHITJAIND/HISTOGRAM/assets/118707073/b155d17d-c85d-44a6-9008-0e414e021716">
</td>
</tr>
</table>

### Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
