# **Finding Lane Lines on the Road** 

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 7 steps. 

First, I converted the images to grayscale, then I applied the Gaussian filter to the images,  and applied Canny edge detection.
Next, I masked the images to region of interest, then I take Hough transform to the images.

In order to draw a single line on the left and right lanes, I modified the hough_lines() function, 'lines' added as return value.
I created single_line() function too.
In single_line(), left and right lane lines are divided by the sign of each line's slope at first.
Then, each line is extrapolated, taken outlier exclusion, calculated averaging weighted by each line length.
(I think the longer lines are, the more reliable in general.)
This averaging line is the result, single line.

If there is no line in averaging process, I take contrast improvment to gray scale image.
Then same process above again, single line calculated.


### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be the false recognition when the car run in the winding road.
And another shortcoming would be the false recognition when the car run in the low contrast road like dark road or almost disappearing line of road.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detecting curvature of road.
This detection will reduce false recognition when the car is running in the winding road.
