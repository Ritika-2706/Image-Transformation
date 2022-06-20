# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
mport the necessary libraries and read the original image and save it as a image variable.

### Step2:
<br>
Read the images using imread() function

### Step3:
<br>
Using calcHist() we can find the histogram of the images.

### Step4:
<br>
Using equalizeHist() we can equalize the image.

### Step5:
<br>
Using matplotlib.pyplot plot the histogram.



## Program:
```python
Developed By:212221240046
Register Number:Ritika S
import numpy as np
import cv2
import matplotlib.pyplot as plt
input_image = cv2.imread("penguin.jpg")
input_image = cv2.cvtColor(input_image,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(input_image)
plt.show()
rows,cols,dim = input_image.shape

# i)Image Translation
M = np.float32([[1,0,100],
               [0,1,200],
               [0,0,1]])
translated_image = cv2.warpPerspective(input_image,M,(cols,rows))
plt.axis('off')
plt.imshow(translated_image)
plt.show()


ii) Image Scaling
M = np.float32([[1.5,0,0],
               [0,1.8,0],
               [0,0,1]])
scaled_image = cv2.warpPerspective(input_image,M,(cols*2,rows*2))
plt.axis('off')
plt.imshow(scaled_image)
plt.show()



iii)Image shearing
M_x = np.float32([[1,0.5,0],
                 [0,1,0],
                 [0,0,1]])
M_y = np.float32([[1,0,0],
                 [0.5,1,0],
                 [0,0,1]])
sheared_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols*1.5),int(rows*1.5)))
sheared_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
plt.imshow(sheared_xaxis)
plt.show()
plt.axis('off')
plt.imshow(sheared_yaxis)
plt.show()



iv)Image Reflection
M_x = np.float32([[1,0,0],
                 [0,-1,rows],
                 [0,0,1]])
M_y = np.float32([[-1,0,cols],
                 [0,1,0],
                 [0,0,1]])
reflected_xaxis = cv2.warpPerspective(input_image,M_x,(int(cols),int(rows)))
reflected_yaxis = cv2.warpPerspective(input_image,M_y,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(reflected_xaxis)
plt.show()
plt.axis('off')
plt.imshow(reflected_yaxis)
plt.show()




v)Image Rotation
angle = np.radians(30)
M = np.float32([[np.cos(angle),-(np.sin(angle)),0],
               [np.sin(angle),np.cos(angle),0],
               [0,0,1]])
rotated_image = cv2.warpPerspective(input_image,M,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotated_image)
plt.show()



vi)Image Cropping
cropped_image = input_image[100:300,100:300]
plt.axis('off')
plt.imshow(cropped_image)
plt.show()




```
## Output:
### i)Image Translation
![ss2](https://user-images.githubusercontent.com/93427238/174631397-504af464-4f5a-47d9-82f9-f162d2762c42.png)



### ii) Image Scaling
![ss3](https://user-images.githubusercontent.com/93427238/174631445-ea503991-6d62-4c57-a592-0579486e6a53.png)




### iii)Image shearing
![ss4](https://user-images.githubusercontent.com/93427238/174631502-ce002de5-4322-447e-8217-28c78f6a82f7.png)



### iv)Image Reflection
![ss5](https://user-images.githubusercontent.com/93427238/174631534-f0c14941-059b-4b28-822a-946484ee652b.png)





### v)Image Rotation
![ss6](https://user-images.githubusercontent.com/93427238/174631562-ccb4e1fa-760b-48fe-b5cf-6d94eb65ede1.png)




### vi)Image Cropping
![ss7](https://user-images.githubusercontent.com/93427238/174631590-49b3f44e-a199-46f3-b6b0-74f13fd5262a.png)






## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
