# Image-Acquisition-from-Web-Cameraa
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
Use VideoCapture(0) to access web camera
<br>

### Step 2:
Use imread to read the video or image
<br>

### Step 3:
Use imwrite to save the image
<br>

### Step 4:
Use imshow to show the video
<br>

### Step 5:
End the program and close the output video windows by pressing 'q'.
<br>

## Program:
``` Python
### Developed By:JEEVAGOWTHAM S
### Register No: 212222230053

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("jeeva.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()



## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()




## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()








```
## Output

### i) Write the frame as JPG image
![Screenshot 2023-09-16 095118](https://github.com/JeevaGowtham-S/Image-Acquisition-from-Web-Cameraa/assets/118042624/c9052c60-eae1-4c68-aae4-41144d235d5c)

</br>
</br>


### ii) Display the video
![Screenshot 2023-09-16 095508](https://github.com/JeevaGowtham-S/Image-Acquisition-from-Web-Cameraa/assets/118042624/3fe28324-9cb6-42f7-84fd-b6611f1986f0)


</br>
</br>


### iii) Display the video by resizing the window

![Screenshot 2023-09-16 094707](https://github.com/JeevaGowtham-S/Image-Acquisition-from-Web-Cameraa/assets/118042624/3700cedd-cbf6-489a-bd10-120ea1570582)

</br>
</br>



### iv) Rotate and display the video
![Screenshot 2023-09-16 094829](https://github.com/JeevaGowtham-S/Image-Acquisition-from-Web-Cameraa/assets/118042624/cec1fc9d-6a74-4364-92ee-47b30ca5d9bf)

</br>
</br>





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
