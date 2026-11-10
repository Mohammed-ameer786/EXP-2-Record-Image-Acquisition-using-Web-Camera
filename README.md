# EXPERIMENT 2

# IMAGE CAPTURE AND VIDEO PROCESSING USING OPENCV

## AIM

To write a Python program using OpenCV to capture an image from the
webcam and perform the following operations:

1.  Save a captured frame as a JPG image.
2.  Display the live webcam video.
3.  Display the video after resizing it to 640 × 480 pixels.
4.  Rotate the video 90° clockwise and display it.

## SOFTWARE REQUIRED

1.  Anaconda -- Python
2.  Jupyter Notebook / VS Code
3.  OpenCV (`cv2`)
4.  NumPy

## ALGORITHM

**Step 1:** Import the required libraries and initialize the webcam
using `cv2.VideoCapture(0)`.

**Step 2:** Check whether the webcam is opened successfully.

**Step 3:** Capture video frames continuously using `cap.read()`.

**Step 4:** Save the first captured frame as `captured_image.jpg` using
`cv2.imwrite()`.

**Step 5:** Display the original live video using `cv2.imshow()`.

**Step 6:** Resize each frame to 640 × 480 pixels using `cv2.resize()`
and display it.

**Step 7:** Rotate each frame 90° clockwise using `cv2.rotate()` and
display it.

**Step 8:** Press the `q` key to stop the video, release the webcam, and
close all display windows.

## PROGRAM

**Developed By:**
Mohammed Ameer F

**Register No.:**
212225040248
``` python
import cv2
import numpy as np

# Initialize the webcam
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Error: Webcam not detected!")
else:
    print("Webcam opened successfully!")

    image_saved = False

    while True:
        # Capture a frame from the webcam
        ret, frame = cap.read()

        if not ret:
            print("Error: Unable to capture video frame!")
            break

        # Save the first frame as a JPG image
        if not image_saved:
            cv2.imwrite("captured_image.jpg", frame)
            print("Image saved as captured_image.jpg")
            image_saved = True

        # 1. Display the original video
        cv2.imshow("Original Video", frame)

        # 2. Resize and display the video
        resized_frame = cv2.resize(frame, (640, 480))
        cv2.imshow("Resized Video", resized_frame)

        # 3. Rotate the video 90 degrees clockwise
        rotated_frame = cv2.rotate(
            frame, cv2.ROTATE_90_CLOCKWISE
        )
        cv2.imshow("Rotated Video", rotated_frame)

        # Press q to exit
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break

    # Release the webcam and close all windows
    cap.release()
    cv2.destroyAllWindows()
    print("Webcam released successfully!")
```

## OUTPUT

### i) Write the frame as JPG image
Image saved successfully as captured_image.jpg


### ii) Display the video
<img width="897" height="647" alt="image" src="https://github.com/user-attachments/assets/4cbfff26-1603-4fce-80b6-5cd3c91da06d" />
The live video is displayed successfully using the OpenCV library.

### iii) Display the video by resizing the window
<img width="687" height="482" alt="image" src="https://github.com/user-attachments/assets/2e4f95c6-8ce0-41a6-90e3-e9ba440c82cd" />
The live video is successfully displayed in a resized window with a resolution of 640 × 480 pixels using the OpenCV library.

### iv) Rotate and display the video
<img width="907" height="607" alt="image" src="https://github.com/user-attachments/assets/b5ab283a-aedb-4192-932f-658eb0a9a0f8" />
The live video is successfully rotated by 90° clockwise and displayed using OpenCV.

## RESULT

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
