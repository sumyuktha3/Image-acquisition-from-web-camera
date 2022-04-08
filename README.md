# Image-Acquisition-from-Web-Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use VideoCapture(0) to access web camera.

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image.

### Step 4:
Use imshow to save the image.

### Step 5:
End the program and close the output video windows by pressing 'q'.


## Program:

### Developed By: S.Sumyuktha Rani
### Register No:212220230050

## i) Write the frame as JPG file
```
import cv2
videoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=videoCaptureObject.read()
    cv2.imwrite("New Picture.jpg",frame)
    result=False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cap.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video
```
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

![pic_1](https://user-images.githubusercontent.com/75235818/162358652-4a99e697-2d7a-448c-8b8c-517ec3e75f68.jpg)

### ii) Display the video

![vid_1](https://user-images.githubusercontent.com/75235818/162358406-c2cfeb39-f956-4ac1-b6e4-3981d8ab1731.jpg)

### iii) Display the video by resizing the window

![vid_2](https://user-images.githubusercontent.com/75235818/162358436-078afdd8-ea4f-4f5a-8240-ef62c793c91c.jpg)


### iv) Rotate and display the video

![vid_3](https://user-images.githubusercontent.com/75235818/162358445-c78e79ec-6a01-40e7-bea5-da5eb1feb193.jpg)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
