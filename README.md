
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.

### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video.

### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` Python
### Developed By: PAVITHRAN MJ
### Register No: 212223240112

## i) Write the frame as JPG file

import cv2
import numpy as np
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("captured_frame.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()


## ii) Display the video
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()




## iii) Display the video by resizing the window
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
![436159317-e6e36dcb-a870-499e-bb71-88fd78ee9e22](https://github.com/user-attachments/assets/5b36da00-8a42-49b1-a539-427d062b22f3)


### ii) Display the video
![436159582-fa12987c-fca3-43fb-9d19-d9455c2b42ff](https://github.com/user-attachments/assets/01e028c3-4e15-40da-ac6b-8c3d9543e1ab)



### iii) Display the video by resizing the window

![436160121-3bdf6d4e-241c-42a7-8d25-300410cb649d](https://github.com/user-attachments/assets/c8078bc5-c7bb-48d1-9b09-1d2e64678e1a)


### iv) Rotate and display the video

![436160369-7c3b7604-2987-416a-86d6-d52997a308a9](https://github.com/user-attachments/assets/a56bd7db-a932-4a6b-9bc1-e36082e577c5)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
