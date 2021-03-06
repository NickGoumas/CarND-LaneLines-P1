# CarND-LaneLines-P1
Udacity Self Driving Car Nanodegree - Finding Lane Lines Project

This is my first project for the Udacity Self Driving Car Nanodegree. The goal was to develop a pipeline to read in video (mp4) files, detect the road lines, and overly them on the output video. The jupyter notebook that contains the pipeline is commented but I'll outline the here briefly.

1. Frame is read in as a color image.
2. Image is converted to greyscale.
3. Gaussian blur is applied to reduce noise and sharpness.
4. Canny edge detection is applied to highlight edges.
5. Mask is applied to image to remove areas where the road lines will not exist. (Sky, far left or right)
6. Hough transform to generate list of lines found in the image.
    1. Sort left and right lines based on slope.
    2. Lines are converted into endpoints.
    3. Linear regression is applied to each side's list if points.
    4. Slope and intercept from regression is used to generate single line for each side.
7. Left and right lines are overlayed on frame.
8. Modified frame is returned.


### Original "White Lane Lines"
![alt text](https://github.com/NickGoumas/CarND-LaneLines-P1/blob/master/output_clips/OriginalWhiteRight.gif?raw=true "Original Video")

### Overlayed "White Lane Lines"
![alt text](https://github.com/NickGoumas/CarND-LaneLines-P1/blob/master/output_clips/OverlayWhiteRight.gif?raw=true "Overlay Video")

### Original "Yellow Lane Lines"
![alt text](https://github.com/NickGoumas/CarND-LaneLines-P1/blob/master/output_clips/OriginalYellowLeft.gif?raw=true "Original Video")

### Overlayed "Yellow Lane Lines"
![alt text](https://github.com/NickGoumas/CarND-LaneLines-P1/blob/master/output_clips/OverlayYellowLeft.gif?raw=true "Overlay Video")

## Not so great "Challenge Video"

### Original
![alt text](https://github.com/NickGoumas/CarND-LaneLines-P1/blob/master/output_clips/OriginalChallenge.gif?raw=true "Original Video")

### Overlayed
![alt text](https://github.com/NickGoumas/CarND-LaneLines-P1/blob/master/output_clips/OverlayChallenge.gif?raw=true "Overlay Video")
