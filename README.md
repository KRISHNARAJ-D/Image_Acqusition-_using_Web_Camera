# Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
```
 Developed By: KRISHNARAJ D
 Register No:  212222230070
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("krishna_12.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()

```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('image',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230070',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```

## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('212222230070',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![q](https://github.com/KRISHNARAJ-D/Image_Acqusition-_using_Web_Camera/assets/119559695/88a7e329-677a-44bd-8f50-4fbff6eef0a9)

</br>
</br>


### ii) Display the video
![q1](https://github.com/KRISHNARAJ-D/Image_Acqusition-_using_Web_Camera/assets/119559695/66355cc7-d3b5-437c-b4b7-7fe8e1d48928)

</br>
</br>


### iii) Display the video by resizing the window
![q3](https://github.com/KRISHNARAJ-D/Image_Acqusition-_using_Web_Camera/assets/119559695/1ee2adc8-2f5e-4ac6-93c5-b11353d20bcb)



</br>
</br>


### iv) Rotate and display the video
![q4](https://github.com/KRISHNARAJ-D/Image_Acqusition-_using_Web_Camera/assets/119559695/e7ff3887-f6cc-4d25-bb6c-76d456d75f83)

</br>
</br>


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
