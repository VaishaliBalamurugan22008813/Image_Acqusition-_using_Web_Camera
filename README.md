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
# Step 1:Use cv2.VideoCapture(0) to access web camera

# Step 2:Use cv2.imread to read the video or image

# Step 3:Use cv2.imwrite to save the image

# Step 4:Use cv2.imshow to show the video

# Step 5:End the program and close the output video window by pressing 'q'.

# Program:
### Developed By:VAISHALIBALAMURUGAN
### Register No:212222230164
# i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
frame_count = 0
while(True):
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"frame_{frame_count}.jpg", frame)
    frame_count += 1
    
    if frame_count >= 100:
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
# ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('OUTPUT',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
# iii) Display the video by resizing the window
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
    cv2.imshow('Vaishali',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
# iv) Rotate and display the video
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
    cv2.imshow('Vaishali',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```




# Output
# i) Write the frame as JPG image
![11](https://github.com/VaishaliBalamurugan22008813/Image_Acqusition-_using_Web_Camera/assets/119390134/caaa7dd3-92bc-4b24-90a6-ed81f2b7a0d8)


# ii) Display the video
![22](https://github.com/VaishaliBalamurugan22008813/Image_Acqusition-_using_Web_Camera/assets/119390134/115235c0-3b9e-43a6-a670-6912bb635b20)


# iii) Display the video by resizing the window
![image](https://github.com/VaishaliBalamurugan22008813/Image_Acqusition-_using_Web_Camera/assets/119390134/3fd246ee-ffc3-4c8c-b6dd-a439cb355148)



# iv) Rotate and display the video
![44](https://github.com/VaishaliBalamurugan22008813/Image_Acqusition-_using_Web_Camera/assets/119390134/b6cdb0c2-a492-4624-bb4f-519d99c18f80)


# Result:
Thus the image is accessed from webcamera and displayed using openCV.
