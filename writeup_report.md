#**Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./output_images/output_solidYellowCurve.png "Solid Yellow Curve"

---

### Reflection

My Pipeline:

1. Convert the image to greyscale.

2. Apply Gaussian Blur to image.

3. Perform Canny Edge Transform to highlight edges.

4. Apply a mask to remove unwanted parts of the image.

5. Perform Hough Transform to detect lines in the image.

6. Sort lines detected into two groups, left and right.

7. Perform linear regression on both groups using Scikit-learn.

8. Compute running average of slope and intercept for each line, over n frames.

9. Draw left and right lines on a blank image using running averages.

10. Merge the "lines" image onto the original to return.

In my code I kept the original ####draw_lines() function as-is to draw the masking vertices. This can be seen in the middle picture below. To draw the required lane lines I created two functions called ####line_reg() and ####draw_side_lines(). 

The ####line_reg() function takes a list of hough lines and a number representing how many previous hough line lists the output will be averaged with. Each time it is called, it seperates the hough lines by slope and assigns them to a left or right group. It then performs a linear regression on each group to determine the slope and intercept of the best-fit line. It then returns these four variables. Two left and two right.

The ####draw_side_lines() function takes the image the lines will eventually be drawn on and teh four variables previously mentioned. It uses the image input to determine the size of the output and is hardcoded to draw lines from the bottom of the image up to the horizontal masking vertex. Using those Y coordinates and the slope and intercepts it solves for the X coordinates for each side. It then uses cv2.line to trace the line. This is output as a black image with transparent lines to be merged with the original image later.


![alt text][image1]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
