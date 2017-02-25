#**Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

###1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

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

In my code I kept the original draw_lines() function as-is to draw the mask vertices.



![alt text][image1]


###2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


###3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
